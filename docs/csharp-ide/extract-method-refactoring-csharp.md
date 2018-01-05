---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-method
title: "메서드 추출 리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Method
- Extract Method refactoring operation [C#]
ms.assetid: eeba11df-a815-4bec-9c21-8a831891b783
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 18fc4c20b39341f884fb23b51822ce7f6e427007
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extract-method-refactoring-c"></a>메서드 추출 리팩터링(C#)
**메서드 추출** 은 쉽게 기존 멤버의 코드 조각에서 새 메서드를 만들 수 있는 방법을 제공 하는 리팩터링 작업 합니다.  
  
 사용 하 여 **메서드 추출**, 선택 된 기존 멤버의 코드 블록 내에서 코드를 추출 하 여 새 메서드를 만들 수 있습니다. 새, 추출 된 메서드에 선택한 코드를 포함 하 고 기존 멤버의 선택 된 코드는 새 메서드를 호출 대체 됩니다. 자체 메서드로 코드의 일부를 설정 하면 신속 하 게 하 고 정확 하 게 다시 사용할 수 있도록 및 가독성 향상에 대 한 코드를 다시 구성.  
  
 **메서드 추출** 다음과 같은 이점을 제공 합니다.  
  
-   좋은 코딩 습관 때문에 개별, 다시 사용할 수 있는 메서드를 강조 합니다.  
  
-   때문에 자체 좋은 조직을 통해 코드를 문서화 합니다.  
  
     설명이 포함 된 이름을 사용 하는 메서드의 가독성 있을 수 자세히과 같은 일련의 주석입니다.  
  
-   재정의 단순화 하는 정밀 메서드 생성을 권장 합니다.  
  
-   코드 중복을 줄입니다.  
  
### <a name="to-use-extract-method"></a>메서드 추출 사용 하려면  
  
1.  `ExtractMethod`이라는 콘솔 응용 프로그램을 만들고 `Program`을 다음 예제 코드로 바꿉니다.  
  
    ```csharp  
    class A  
    {  
        const double PI = 3.141592;  
  
        double CalculatePaintNeeded(double paintPerUnit, double radius)  
        {  
            // Select any of the following:  
            // 1. The entire next line of code.  
            // 2. The right-hand side of the next line of code.  
            // 3. Just "PI *" of the right-hand side of the next line  
            //    of code (to see the prompt for selection expansion).  
            // 4.  All code within the method body.  
            // ...Then invoke Extract Method.  
  
            double area = PI * radius * radius;  
  
            return area / paintPerUnit;  
        }  
    }  
    ```  
  
2.  추출 하려는 코드 조각을 선택 합니다.  
  
    ```csharp  
    double area = PI * radius * radius;  
    ```  
  
3.  에 **리팩터링** 메뉴를 클릭 하 여 **메서드 추출**합니다.  
  
     **메서드 추출** 대화 상자가 나타납니다.  
  
     또는 바로 가기 키 CTRL + R, 표시 하려면 M도 입력할 수는 **메서드 추출** 대화 상자.  
  
     선택한 스키마 코드를 가리키도록 **리팩터링**, 클릭 하 고 **메서드 추출** 표시 하는 **메서드 추출** 대화 상자.  
  
4.  과 같은 새 메서드의 이름을 지정 `CircleArea`에 **새 메서드 이름** 상자입니다.  
  
     새 메서드 서명 미리 보기가 표시 됩니다 **메서드 시그니처 미리 보기**합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="remarks"></a>설명  
 사용 하는 경우는 **메서드 추출** 명령을 새 메서드는 동일한 클래스의 소스 멤버 뒤에 삽입 됩니다.  
  
## <a name="partial-types"></a>부분 형식(Partial Type)  
 클래스 형식인 경우 부분을 다음 **메서드 추출** 원본 멤버 바로 뒤에 새 메서드를 생성 합니다. **메서드 추출** 인스턴스 데이터가 없는 new 메서드의 코드에서 참조 하는 경우 정적 메서드를 만들어 새 메서드의 시그니처를 확인 합니다.  
  
## <a name="generic-type-parameters"></a>제네릭 형식 매개 변수  
 생성된 된 코드를 추가 하지 것입니다는 제한 되지 않은 제네릭 형식 매개 변수가 있는 메서드를 추출 하는 경우는 `ref` 해당 매개 변수에 한정자에 값을 할당 하지 않는 한 합니다. 추출된 된 메서드가 참조 형식을 제네릭 형식 인수로 지원할 경우 수동으로 추가 해야는 `ref` 메서드 시그니처의 매개 변수 한정자입니다.  
  
## <a name="anonymous-methods"></a>무명 메서드  
 지역 변수 선언 되거나 무명 메서드 외부에서 참조에 대 한 참조를 포함 하는 무명 메서드의의 부분을 추출 하려고 하면 다음 Visual Studio에 대해 경고 의미 체계가 변경 될 합니다.  
  
 무명 메서드는 지역 변수의 값을 사용 하는 값은 익명 메서드가 실행 되는 순간 가져옵니다. 무명 메서드를 다른 메서드를 추출할 때 지역 변수의 값 압축 푼된 메서드를 호출 하는 시점에서 가져옵니다.  
  
 다음 예제는이 의미 체계 변경입니다. 이 코드를 실행 하면 다음 **11** 콘솔에 표시 됩니다. 사용 하는 경우 **메서드 추출** 을 자체 메서드로 코드 주석으로 표시 된 코드 영역을 풀고 다음 리팩터링된 코드를 다음 실행 **10** 콘솔에 표시 됩니다.  
  
```csharp  
class Program  
{  
    delegate void D();  
    D d;  
    static void Main(string[] args)  
    {  
        Program p = new Program();  
        int i = 10;  
        /*begin extraction*/  
            p.d = delegate { Console.WriteLine(i++); };  
        /*end extraction*/  
        i++;  
        p.d();  
    }  
}  
```  
  
 이 문제를 해결 하려면 클래스의 무명 메서드 필드에 사용 되는 지역 변수 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리팩터링(C#)](refactoring-csharp.md)