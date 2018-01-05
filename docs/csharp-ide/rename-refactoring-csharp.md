---
redirect_url: /visualstudio/csharp-ide/refactoring/rename
title: "이름 바꾸기 리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Rename
- Rename refactoring [C#]
ms.assetid: 268942fc-b142-4dfa-8d90-bedd548c2e4f
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 42c5f99b3bf5ba95bc279cd5e117745ccc8e02c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="rename-refactoring-c"></a>이름 바꾸기 리팩터링(C#)
**이름 바꾸기** 는 필드, 지역 변수, 메서드, 네임 스페이스, 속성 및 형식 등의 코드 기호에 대 한 식별자 이름을 바꿀 수 있는 간편한 방법을 제공 하는 Visual Studio 통합된 개발 환경 (IDE)에서 리팩터링 기능입니다. **이름 바꾸기** 주석 문자열 이름을 변경 하 고 선언과 식별자의 호출을 사용할 수 있습니다.  
  
> [!NOTE]
>  Visual Studio에 대 한 소스 제어를 사용 하는 경우 이름 바꾸기 리팩터링 수행 하려고 하기 전에 소스의 최신 버전을 가져옵니다.  
  
 이름 바꾸기 리팩터링 다음 Visual Studio 기능에서 제공 됩니다.  
  
|기능|IDE에서의 리팩터링의 동작|  
|-------------|----------------------------------------|  
|코드 편집기|특정 유형의 코드 기호에 커서를 배치 하는 경우 코드 편집기에서 사용할 수는 이름 바꾸기 리팩터링 합니다. 이 위치에 커서를 호출할 수 있습니다는 **이름 바꾸기** 바로 가기 키 (Ctrl + R, Ctrl + R)을 입력 하거나 선택 하 여 명령을 **이름 바꾸기** 빠른 작업을 바로 가기 메뉴에서 명령을 또는 **리팩터링** 메뉴.|  
|클래스 뷰|클래스 뷰에서 식별자를 선택 하는 경우 바로 가기 메뉴에서 사용할 수는 이름 바꾸기 리팩터링 및 **리팩터링** 메뉴.|  
|개체 브라우저|개체 브라우저에서 식별자를 선택 하는 경우 이름 바꾸기 리팩터링는 에서만 사용할 수는 **리팩터링** 메뉴.|  
|Windows Forms 디자이너의 속성 표|에 **속성 표** Windows Forms 디자이너의 컨트롤의 이름을 변경 작업이 시작 됩니다 이름 바꾸기 해당 컨트롤에 대 한 합니다. **이름 바꾸기** 대화 상자가 나타나지 것입니다.|  
|솔루션 탐색기|**솔루션 탐색기**, **이름 바꾸기** 명령은 바로 가기 메뉴에서 사용할 수 있습니다. 선택한 소스 파일에 클래스 이름이 파일 이름과 동일 클래스 있으면 동시에 소스 파일 이름을 바꾸고 이름 바꾸기 리팩터링 실행이 명령을 사용할 수 있습니다.<br /><br /> 예를 들어 기본 Windows 기반 응용 프로그램을 만들고 이름을 하 여 Form1.cs TestForm.cs로 경우 소스 파일 이름과 Form1.cs는 TestForm.cs 및 Form1 클래스를 변경 되 고의 모든 참조 클래스 TestForm 이름이 변경 됩니다. **참고:** 는 **실행 취소** 명령 (CTRL + Z)만 이름 바꾸기 리팩터링 코드에 실행 취소 되며 파일 이름을 원래 이름으로 다시 변경 하지는 것입니다. <br /><br /> 선택한 소스 파일에 클래스 파일 이름과 같은 이름이 없는 경우는 **이름 바꾸기** 명령을 **솔루션 탐색기** 소스 파일 이름만 바꾸고 이름 바꾸기는 실행 되지 것입니다 리팩터링 합니다.|  
  
## <a name="rename-operations"></a>작업 이름 바꾸기  
 실행 하는 동안 **이름 바꾸기**, 리팩터링 엔진 다음 표에 설명 된 대로 각 코드 기호와 관련 된 이름 바꾸기 작업을 수행 합니다.  
  
|코드 기호|이름 바꾸기 작업|  
|-----------------|----------------------|  
|필드|새 이름으로 선언 및 필드의 용도 변경합니다.|  
|지역 변수|새 이름으로 선언과 변수 사용을 변경합니다.|  
|메서드|메서드와 해당 메서드에 대 한 모든 참조의 이름을 새 이름으로 변경합니다. **참고:** 확장 메서드를 바꾸면 이름 바꾸기 작업 확장 메서드는 정적 메서드 또는 인스턴스 메서드로 사용 되 고 여부에 관계 없이 범위에 있는 메서드의 모든 인스턴스에 전달 합니다. 자세한 내용은 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)를 참조하세요.|  
|네임스페이스|네임 스페이스의 이름을 선언에서 새 이름으로 변경 모든 `using` 문과 정규화 된 이름입니다. **참고:** 네임 스페이스의 이름을 바꿀 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도 업데이트는 **Default Namespace** 속성에는 **응용 프로그램** 의 페이지는 **프로젝트 디자이너**. 이 속성을 선택 하 여 다시 설정할 수 없습니다 **실행 취소** 에서 **편집** 메뉴. 다시 설정 하는 **Default Namespace** 속성 값의 속성을 수정 해야는 **프로젝트 디자이너**합니다. 자세한 내용은 참조 [응용 프로그램 페이지](../ide/reference/application-page-project-designer-csharp.md)합니다.|  
|속성|새 이름으로 선언 및 속성의 용도 변경합니다.|  
|형식|생성자 및 소멸자를 포함 하 여 새 이름으로 모든 선언 및 형식의 모든 용도 변경 합니다. 부분 형식에 대 한 이름 바꾸기 작업이 모든 부분에 전파 됩니다.|  
  
#### <a name="to-rename-an-identifier"></a>식별자의 이름을 바꾸려면  
  
1.  `RenameIdentifier`이라는 콘솔 응용 프로그램을 만들고 `Program`을 다음 예제 코드로 바꿉니다.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  에 커서를 놓고 `MethodB`를 메서드 선언 또는 메서드를 호출 합니다.  
  
3.  **리팩터링** 메뉴 선택 **이름 바꾸기**합니다. **이름 바꾸기** 대화 상자가 나타납니다.  
  
     커서를을 마우스 오른쪽 단추로 클릭 가리킨 **리팩터링** 클릭 한 다음의 상황에 맞는 메뉴에 **이름 바꾸기** 표시 하는 **이름 바꾸기** 대화 상자.  
  
4.  에 **새 이름을** 필드를 입력 `MethodC`합니다.  
  
5.  선택 된 **주석에서 검색** 확인란 합니다.  
  
6.  **확인**을 클릭합니다.  
  
7.  에 **변경 내용 미리 보기** 대화 상자를 클릭 **적용**합니다.  
  
#### <a name="to-rename-an-identifier-using-quick-actions"></a>빠른 작업을 사용 하는 식별자의 이름을 바꾸려면  
  
1.  `RenameIdentifier`이라는 콘솔 응용 프로그램을 만들고 `Program`을 다음 예제 코드로 바꿉니다.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  선언에 `MethodB`를 입력 하거나 메서드 식별자 백스페이스 키입니다. 빠른 작업 전구가 여백에 표시 됩니다.  
  
    > [!NOTE]
    >  이름 바꾸기 리팩터링 빠른 작업을 사용 하 여 식별자 선언에만 호출할 수 있습니다.  
  
3.  바로 가기 입력 **Shift + Alt + f 10** 바로 가기 메뉴를 표시 합니다.  
  
     또는  
  
     바로 가기 메뉴를 표시 하려면 전구 옆에 있는 검정색 삼각형을 클릭 합니다.  
  
4.  선택 된 **이름 바꾸기 '\<identifer1 >'에 '\<identifier2 >'** 메뉴 항목 이름 바꾸기 리팩터링을 호출을 합니다. 에 대 한 모든 참조  **\<identifer1 >** 자동으로 업데이트할지  **\<identifier2 >**합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="renaming-implemented-or-overridden-members"></a>구현 되거나 재정의 된 멤버 이름 바꾸기  
 때 있습니다 **이름 바꾸기** 구현/재정의 되거나 구현 재정의/다른 형식에 멤버는 멤버 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 이름 바꾸기 작업을 모두 업데이트 수행 하면 라는 대화 상자가 표시 됩니다. 클릭 하면 **계속**, 리팩터링 엔진 재귀적으로 찾아 자료의 모든 멤버의 이름을 바꿉니다 및 파생된 형식의 구현/재정의 관계 이름을 바꾸는 멤버와 함께 합니다.  
  
 다음 코드 예제에서는 구현/재정의 관계를 가진 멤버를 포함 합니다.  
  
 [!code-csharp[CsUsingCsIDERefactor#1](../csharp-ide/codesnippet/CSharp/rename-refactoring-csharp_1.cs)]  
  
 이전 예에서 이름 바꾸기 `C.Method()` 또한의 이름도 바꿉니다 `Ibase.Method()` 때문에 `C.Method()` 구현 `Ibase.Method()`합니다. 다음으로 리팩터링 엔진을 재귀적으로 확인 하는 `Ibase.Method()` 구현한 `Derived.Method()` 바꿉니다 `Derived.Method()`합니다. 리팩터링 엔진 이름은 바뀌지 않습니다 `Base.Method()`때문에, `Derived.Method()` 재정의 하지 않는 `Base.Method()`합니다. 리팩터링 엔진이 없는 경우 여기서 중지 **오버 로드 이름 바꾸기** 체크 인 된 **이름 바꾸기** 대화 상자.  
  
 경우 **오버 로드 이름 바꾸기** 을 선택 하면 리팩터링 엔진의 이름을 바꿉니다 `Derived.Method(int i)` 오버 로드 하므로 `Derived.Method()`, `Base.Method(int i)` 의해 재정의 되므로 때문에 `Derived.Method(int i)`, 및 `Base.Method()` 의 오버 로드 되었기 때문에 `Base.Method(int i)`.  
  
> [!NOTE]
>  참조 된 어셈블리에 정의 된 멤버의 이름을 바꾸면 이름을 바꾸는 빌드 오류가 발생 하는 대화 상자 설명 합니다.  
  
## <a name="renaming-properties-of-anonymous-types"></a>익명 형식의 속성 이름 바꾸기  
 익명 형식의 속성의 이름을 바꿀 때는 이름 바꾸기 작업이 동일한 속성이 있는 익명 형식의 다른 속성에 전파 됩니다. 다음 예에서는이 동작을 보여 줍니다.  
  
```csharp  
var a = new { ID = 1};  
var b = new { ID = 2};  
```  
  
 위의 코드에서 이름 바꾸기 `ID` 바뀝니다 `ID` 두 문의 동일한 기본 익명 형식을 갖기 때문입니다.  
  
```csharp  
var companyIDs =  
    from c in companylist  
    select new { ID = c.ID, Name = c.Name};  
  
var orderIDs =  
    from o in orderlist  
    select new { ID = o.ID, Item = o.Name};  
```  
  
 위의 코드에서 이름 바꾸기 `ID` 의 한 인스턴스 이름을 바꿀만 됩니다 `ID` 때문에 `companyIDs` 및 `orderIDs` 동일한 속성이 없는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리팩터링(C#)](refactoring-csharp.md)   
 [익명 형식](/dotnet/csharp/programming-guide/classes-and-structs/anonymous-types)