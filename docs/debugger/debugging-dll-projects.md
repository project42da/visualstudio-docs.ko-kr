---
title: "DLL 프로젝트 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 05/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- templates, debugging DLLs
- DLLs, debugging
- debugging [Visual Studio], DLLs
ms.assetid: 433cab30-d191-460b-96f7-90d2530ca243
caps.latest.revision: "38"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92d888c04827f3df2c9bc5ede33d4dfd9a6742dc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-dll-projects-from-visual-studio"></a>Visual Studio에서 DLL 프로젝트 디버깅
다음 Visual Studio 템플릿 Dll을 만듭니다.  
  
-   (C++, C# 및 Visual Basic): 클래스 라이브러리   

-   (C + +): Win32 콘솔 DLL 프로젝트
  
     자세한 내용은 [MFC Debugging Techniques](../debugger/mfc-debugging-techniques.md)을 참조하세요.

-   (C++, C# 및 Visual Basic): Windows Forms 컨트롤 라이브러리
  
     Windows Forms 컨트롤 라이브러리를 디버깅 하는 것으로 클래스 라이브러리 프로젝트를 디버깅 하는 것과 비슷합니다. 대부분의 경우에 다른 프로젝트에서 Windows 컨트롤을 호출하게 됩니다. 따라서 호출하는 프로젝트를 디버깅할 때 Windows 컨트롤의 코드를 단계별로 실행하고, 중단점을 설정하고, 다른 디버깅 작업을 수행할 수 있습니다. 자세한 내용은 [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index)을 참조하십시오.  

  
##  <a name="vxtskdebuggingdllprojectsbuildingadebugversion"></a> Building a debug version  
 어떤 방법으로 디버깅을 시작하든지 먼저 DLL의 디버그 버전을 빌드하여 응용 프로그램에서 검색할 위치에 저장해야 합니다. 만약 이 단계를 생략하면 응용 프로그램에서는 다른 DLL 버전을 찾아서 로드할 수 있습니다. 그러면 프로그램은 계속 실행되지만 중단점에는 도달하지 않습니다. 디버깅 작업을 수행할 때 디버거의 **모듈** 창을 열어 프로그램에서 로드한 DLL을 확인할 수 있습니다. **모듈** 창에는 디버깅 중인 프로세스에서 로드한 각 DLL 또는 EXE가 표시됩니다. 자세한 내용은 [How to: Use the Modules Window](../debugger/how-to-use-the-modules-window.md)을 참조하십시오.  
 디버거에서 C++로 작성된 코드에 연결하려면 코드에서 `DebuggableAttribute`를 내보내야 합니다. 이 특성은 [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) 링커 옵션으로 링크하여 자동으로 코드에 추가할 수 있습니다.  
  
##  <a name="vxtskdebuggingdllprojectsmixedmodedebugging"></a> Mixed-Mode debugging  
 DLL을 호출하는 호출 응용 프로그램은 관리 코드로 작성될 수도 있고 네이티브 코드로 작성될 수도 있습니다. 네이티브 코드가 관리되는 DLL을 호출하고 두 코드를 모두 디버깅해야 하는 경우에는 관리되는 디버거와 네이티브 디버거를 모두 활성화해야 합니다. 이 선택할 수는  **\<프로젝트 > 속성 페이지** 대화 상자 또는 창. 이를 수행하는 방법은 DLL 프로젝트에서 디버깅을 시작하는지 아니면 호출 응용 프로그램 프로젝트에서 디버깅을 시작하는지에 따라 달라집니다. 자세한 내용은 [How to: Debug in Mixed Mode](../debugger/how-to-debug-in-mixed-mode.md)을 참조하십시오.  
  
##  <a name="vxtskdebuggingdllprojectschangingdefaultconfigurations"></a> Changing default configurations  
 프로젝트 템플릿을 사용하여 콘솔 응용 프로그램 프로젝트를 만들면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서는 디버그 및 릴리스 구성에 필요한 설정을 자동으로 만듭니다. 필요하면 이 설정을 변경할 수 있습니다. 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md), [C# 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md), [Visual Basic 디버그 구성에 대 한 프로젝트 설정 ](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), 및 [하는 방법: 디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다.  
  
##  <a name="vxtskdebuggingdllprojectswaystodebugthedll"></a> Ways to debug the DLL  
 이 단원의 각 프로젝트에서는 DLL을 만듭니다. DLL은 직접 실행할 수 없습니다. DLL은 일반적으로 EXE와 같은 응용 프로그램에서 호출해야 합니다. 자세한 내용은 [Creating and Managing Visual C++ Projects](/cpp/ide/creating-and-managing-visual-cpp-projects)을 참조하세요. 호출 응용 프로그램은 다음 기준 중 하나에 부합해야 합니다.  
  
-   동일한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션에서 클래스 라이브러리를 포함한 다른 프로젝트에 내장된 응용 프로그램  
  
-   테스트 컴퓨터나 프로덕션 컴퓨터에 이미 배포된 기존 응용 프로그램  
  
-   웹에 설치되어 URL을 통해 액세스할 수 있는 응용 프로그램  
  
-   DLL을 포함하는 웹 페이지가 들어 있는 웹 응용 프로그램  
  
###  <a name="vxtskdebuggingdllprojectsthecallingapplication"></a> Debugging the calling application  
DLL을 디버깅하려면 호출 응용 프로그램 디버깅을 먼저 시작해야 합니다. 호출 응용 프로그램은 일반적으로 EXE 또는 웹 응용 프로그램입니다. 이를 디버깅하는 데는 여러 가지 방법이 있습니다.  
  
-   호출 응용 프로그램에 대한 프로젝트가 있으면 이 프로젝트를 열고 **디버그** 메뉴에서 실행 파일을 시작할 수 있습니다. 자세한 내용은 참조 [디버거 시작](../debugger/getting-started-with-the-debugger.md)합니다.  
  
-   호출 응용 프로그램이 테스트 컴퓨터나 프로덕션 컴퓨터에 이미 배포되어 실행되고 있는 기존의 프로그램인 경우 이 응용 프로그램에 연결할 수 있습니다. DLL이 Internet Explorer로 호스팅된 컨트롤이거나 웹 페이지의 컨트롤인 경우 이 방법을 사용합니다. 자세한 내용은 [How to: Attach to a Running Process](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)을 참조하십시오.  
  
-   DLL 프로젝트에서 이를 디버깅할 수 있습니다. 자세한 내용은 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)을 참조하세요.  
  
-   이 디버깅할 수는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [직접 실행 창](#vxtskdebuggingdllprojectstheimmediatewindow)합니다. 이 경우 **직접 실행** 창은 응용 프로그램 역할을 수행합니다.  
  
호출 응용 프로그램에 대한 디버깅을 시작하기 전에, 일반적으로 클래스 라이브러리에 중단점을 설정합니다. 자세한 내용은 [Using Breakpoints](../debugger/using-breakpoints.md)을 참조하세요. 중단점에 도달하면 각 줄의 작업을 확인하면서 코드를 단계별로 실행하여 문제를 해결할 수 있습니다. 자세한 내용은 참조 [디버거에서 코드를 탐색](../debugger/navigating-through-code-with-the-debugger.md)합니다.
  
###  <a name="vxtskdebuggingdllprojectstheimmediatewindow"></a> 직접 실행 창  
 호출 응용 프로그램을 사용하지 않고도 DLL의 함수 및 메서드를 실행할 수 있습니다. 디자인 타임 디버깅을 수행하고 **직접 실행** 창을 사용할 수 있습니다. 이러한 방식으로 디버깅하려면 DLL 프로젝트가 열려 있는 상태에서 다음 단계를 수행합니다.  
  
1.  디버거 **직접 실행** 창을 엽니다.  
  
2.  `Test` 클래스의 `Class1`라는 메서드를 테스트하려면 직접 실행 창에 다음 C# 코드를 입력하여 `Class1` 형식의 개체를 인스턴스화합니다. 구문을 적절하게 변경하면 이 관리 코드는 Visual Basic 및 C++에서 작동합니다.  
  
    ```  
    Class1 obj = new Class1();  
    ```  
  
     C#에서 모든 이름은 정규화되어야 합니다. 또한 모든 메서드나 변수는 디버깅 세션의 현재 범위와 컨텍스트에 있어야 합니다.  
  
3.  `Test` 에서 `int` 매개 변수 하나를 사용하는 것으로 가정하고 `Test` 직접 실행 **창을 사용하여** 를 실행합니다.  
  
    ```  
    ?obj.Test(10)  
    ```  
  
     **직접 실행** 창에 결과가 출력됩니다.  
  
4.  `Test` 내에 중단점을 배치한 다음 함수를 다시 실행하여 이 메서드를 계속 디버깅할 수 있습니다.  
  
    ```  
    ?obj.Test(10);  
    ```  
  
     중단점에 도달하면 `Test`를 단계별로 실행할 수 있습니다. `Test`실행을 마치면 디버거가 디자인 모드로 되돌아갑니다.

## <a name="vxtskdebuggingdllprojectsexternal"></a>C + + 프로젝트에서를 외부 DLL 디버깅

(예: 코드를 단계별로) 사용할 수 있는 디버깅 기능에 따라 달라 집니다 외부 DLL 프로젝트를 디버깅 하는 경우는 [DLL의 디버그 구성을](#vxtskdebuggingdllprojectsbuildingadebugversion) 여부와 작성 했을 때의 [.pdb파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) 및 DLL에 대 한 다른 필수 파일을 사용할 수 있습니다.

프로젝트가는 DLL 및 디버깅에 사용 되는.pdb 파일을 찾을 수 있어야 합니다. 이러한 파일을 복사 하는 사용자 지정 빌드 작업을 만들 수는  **\<프로젝트 폴더 > \Debug** 출력 폴더 또는 있습니다 수 파일 출력 폴더에 수동으로 복사 합니다.

속성 페이지에서 *.lib 파일과 헤더 파일의 위치를 쉽게 설정할 수 있습니다 (c + + 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성 보기**를 선택한 후 **모든 구성**)를 복사할 필요 없이 출력 폴더에 해당 합니다.

- 헤더 파일에 있는 폴더를 지정 하는 C/c + + 폴더 (일반 범주)-는 **추가 포함 디렉터리** 필드입니다.
- .Lib 파일에 있는 폴더를 지정 하는 링커 폴더 (일반 범주)-는 **추가 라이브러리 디렉터리** 필드입니다. 
- 전체 경로 파일 이름을.lib 파일에 대 한 링커 폴더 (입력 범주)-지정 된 **추가 종속성** 필드입니다.

구성이 정확 하면에서 실행을 시작 하 여 디버그할 수 있습니다는 **디버그** 메뉴.

프로젝트 설정에 대 한 자세한 내용은 참조 하십시오. [속성 페이지 (Visual c + +)](/cpp/ide/property-pages-visual-cpp)합니다.
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [Visual c + + 프로젝트 형식](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [C#에 대 한 프로젝트 설정 디버그 구성](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [디버그 구성에 대 한 Visual Basic 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [디버거 보안](../debugger/debugger-security.md)