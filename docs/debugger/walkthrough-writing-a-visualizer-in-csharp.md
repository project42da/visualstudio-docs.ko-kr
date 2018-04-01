---
title: '연습: C#에서 시각화 도우미 작성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: 53467461-8e0f-45ee-9bc4-374bbaeaf00f
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6e161b3c914d0a87a720f1217b52a571b85f5ff9
ms.sourcegitcommit: 03a74d29a1e0584ff4808ce6c9e812b51e774905
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2018
---
# <a name="walkthrough-writing-a-visualizer-in-c"></a>연습: C#에서 시각화 도우미 작성 #
이 연습에서는 C#을 사용 하 여 간단한 시각화 도우미를 작성 하는 방법을 보여 줍니다. 이 연습에서 만들 시각화 도우미는 Windows forms 메시지 상자를 사용 하 여 문자열의 내용을 표시 합니다. 이 간단한 문자열 시각화 도우미 자체에서 특히 유용 하지 않습니다. 하지만 다른 데이터 형식에 대 한 보다 유용한 시각화 도우미를 만들기 위해 수행 해야 하는 기본 단계를 보여 줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경 하려면로 이동 된 **도구** 메뉴 선택 **설정 가져오기 및 내보내기**합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 시각화 도우미 코드는 디버거에서 읽을 DLL에 배치 되어야 합니다. 따라서 첫 번째 단계는 DLL에 대 한 클래스 라이브러리 프로젝트를 만드는 것입니다.  

## <a name="create-a-visualizer-manually"></a>시각화 도우미를 수동으로 만들기

시각화 도우미를 만들려면 아래 작업을 수행 합니다.
  
#### <a name="to-create-a-class-library-project"></a>클래스 라이브러리 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로 만들기 > 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 **Visual C#**선택, **.NET 표준**합니다.  
  
3.  가운데 창에서 선택 **클래스 라이브러리**합니다.  
  
4.  에 **이름** 상자에 MyFirstVisualizer 같이 클래스 라이브러리에 대 한 적절 한 이름을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
 클래스 라이브러리를 만든 후에 정의 된 클래스를 있습니다 사용할 수 있도록 Microsoft.VisualStudio.DebuggerVisualizers.DLL에 대 한 참조를 추가 해야 합니다. 그러나 참조를 추가 하기 전에 바꿔야 일부 클래스 의미 있는 이름을 갖도록 합니다.  
  
#### <a name="to-rename-class1cs-and-add-microsoftvisualstudiodebuggervisualizers"></a>Class1.cs의 이름을 바꾸고 Microsoft.VisualStudio.DebuggerVisualizers를 추가 하려면  
  
1.  **솔루션 탐색기**Class1.cs를 마우스 오른쪽 단추로 클릭 하 고 선택 **이름 바꾸기** 바로 가기 메뉴.  
  
2.  DebuggerSide.cs 같은 의미 있는 이름을 Class1.cs에서 변경 합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]새 파일 이름과 일치 하도록 DebuggerSide.cs의 클래스 선언이 자동으로 변경 합니다.  
  
3.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조** 선택 **참조 추가** 바로 가기 메뉴.  
  
4.  에 **참조 추가** 대화 상자의 **.NET** 탭에서 Microsoft.VisualStudio.DebuggerVisualizers.DLL을 선택 합니다.  
  
5.  **확인**을 클릭합니다.  
  
6.  DebuggerSide.cs에서 다음 문을 `using` 문에 추가합니다.  
  
    ```csharp  
    using Microsoft.VisualStudio.DebuggerVisualizers;  
    ```  
  
 이제 디버거 쪽 코드를 만들 준비가 되었습니다. 이는 시각화하려는 정보를 표시하기 위해 디버거 내에서 실행되는 코드입니다. 먼저,의 선언을 변경 해야는 `DebuggerSide` 개체의 기본 클래스에서 상속 `DialogDebuggerVisualizer`합니다.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>DialogDebuggerVisualizer에서 상속하려면  
  
1.  DebuggerSide.cs에서 다음 코드 줄으로 이동 합니다.  
  
    ```csharp  
    public class DebuggerSide  
    ```  
  
2.  코드를 변경 합니다.  
  
    ```csharp  
    public class DebuggerSide : DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer`에 하나의 추상 메서드 (`Show`) 재정의 해야 합니다.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>DialogDebuggerVisualizer.Show 메서드를 재정의하려면  
  
-   `public class DebuggerSide`, 다음 추가 **메서드:**  
  
    ```csharp  
    protected override void Show(IDialogVisualizerService windowService, IVisualizerObjectProvider objectProvider)  
    {  
    }  
    ```  
  
 `Show` 메서드 실제로 시각화 도우미 대화 상자 또는 기타 사용자 인터페이스를 만들고 디버거에서 시각화 도우미로 전달 된 정보를 표시 하는 코드를 포함 합니다. 대화 상자를 만들고 정보를 표시하는 코드를 추가해야 합니다. 이 연습에서는 있습니다 Windows forms 메시지 상자를 사용 하 여이 위해 됩니다. 참조를 추가 해야 하는 먼저 및 `using` System.Windows.Forms에 대 한 문입니다.  
  
#### <a name="to-add-systemwindowsforms"></a>System.Windows.Forms을 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조** 선택 **참조 추가** 바로 가기 메뉴.  
  
2.  에 **참조 추가** 대화 상자의 **.NET** 탭, System.Windows.Forms.DLL를 선택 합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  DebuggerSide.cs에서 다음 문을 `using` 문에 추가합니다.  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
 이제, 작성 및 시각화 도우미에 대 한 사용자 인터페이스를 표시 하는 코드를 추가 합니다. 첫 번째 시각화 도우미 이기 때문에 사용자 인터페이스를 간단 하 게 유지 하 고 메시지 상자를 사용 합니다.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>대화 상자에서 시각화 도우미 출력을 표시 하려면  
  
1.  `Show` 메서드에 다음 코드 줄을 추가합니다.  
  
    ```csharp  
    MessageBox.Show(objectProvider.GetObject().ToString());  
    ```  
  
     이 예제 코드에는 오류 처리 기능이 포함되어 있지 않습니다. 실제 시각화 도우미 나 기타 유형의 응용 프로그램의 오류 처리를 포함 해야 합니다.  
  
2.  에 **빌드** 메뉴 선택 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
 디버거 쪽 코드의 끝입니다. 없는 다음 하나의 단계가 더을 권장 합니다. 시각화 도우미를 구성 하는 클래스의 컬렉션을 디버기 쪽에 알리는 특성이 필요 합니다.  
  
#### <a name="to-add-the-debuggee-side-code"></a>디버기 쪽 코드를 추가 하려면  
  
1.  DebuggerSide.cs에 다음 특성 코드 뒤에 추가 된 `using` 문의 하기 전에 `namespace MyFirstVisualizer`:  
  
    ```csharp  
    [assembly:System.Diagnostics.DebuggerVisualizer(  
    typeof(MyFirstVisualizer.DebuggerSide),  
    typeof(VisualizerObjectSource),  
    Target = typeof(System.String),  
    Description = "My First Visualizer")]  
    ```  
  
2.  에 **빌드** 메뉴 선택 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
 이제 첫 번째 시각화 도우미가 완성되었습니다. 각 단계를 올바르게 수행했으면 시각화 도우미를 빌드하고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치할 수 있을 것입니다. 그러나 시각화 도우미를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치하기 전에 이를 테스트하여 올바르게 실행되는지 확인해야 합니다. 이제 시각화 도우미를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치하지 않고 실행하는 테스트 환경을 만듭니다.  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>시각화 도우미를 표시 하기 위한 테스트 메서드를 추가 하려면  
  
1.  `public DebuggerSide` 클래스에 다음 메서드를 추가합니다.  
  
    ```csharp  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost visualizerHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       visualizerHost.ShowVisualizer();  
    }  
    ```  
  
2.  에 **빌드** 메뉴 선택 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
 이제 시각화 도우미 DLL을 호출하기 위한 실행 파일 프로젝트를 만들어야 합니다. 간단히 하기 위해 콘솔 응용 프로그램 프로젝트를 사용 합니다.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>솔루션에 콘솔 응용 프로그램 프로젝트를 추가하려면  
  
1.  에 **파일** 메뉴 선택 **추가** 클릭 하 고 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트 추가** 대화 상자는 **템플릿** 상자 **콘솔 응용 프로그램**합니다.  
  
3.  에 **이름** 상자와 같은 콘솔 응용 프로그램에 대 한 의미 있는 이름을 입력 합니다 `MyTestConsole`합니다.  
  
4.  **확인**을 클릭합니다.  
  
 이제 MyTestConsole에서 MyFirstVisualizer를 호출하는 데 필요한 참조를 추가해야 합니다.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>MyTestConsole에 필요한 참조를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyTestConsole** 선택 **참조 추가** 바로 가기 메뉴.  
  
2.  에 **참조 추가** 대화 상자, **.NET** 탭에서 Microsoft.VisualStudio.DebuggerVisualizers.DLL을 선택 합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **MyTestConsole** 선택 **참조 추가** 다시 합니다.  
  
5.  에 **참조 추가** 대화 상자를 클릭는 **프로젝트** 탭 한 다음 MyFirstVisualizer를 클릭 합니다.  
  
6.  **확인**을 클릭합니다.  
  
 이제 테스트 환경을 끝내기 위한 코드를 추가합니다.  
  
#### <a name="to-add-code-to-mytestconsole"></a>MyTestConsole에 코드를 추가하려면  
  
1.  **솔루션 탐색기**Program.cs를 마우스 오른쪽 단추로 클릭 하 고 선택 **이름 바꾸기** 바로 가기 메뉴.  
  
2.  좀 더 의미 있는, TestConsole.cs 같은 Program.cs에서 이름을 편집 합니다.  
  
     **참고** [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 새 파일 이름과 일치 하도록 TestConsole.cs의 클래스 선언이 자동으로 변경 합니다.  
  
3.  TestConsole.cs, 다음 코드를 추가 `using` 문:  
  
    ```csharp  
    using MyFirstVisualizer;  
    ```  
  
4.  `Main` 메서드에 다음 코드를 추가합니다.  
  
    ```csharp  
    String myString = "Hello, World";  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
 이제 첫 번째 시각화 도우미를 테스트할 준비가 됩니다.  
  
#### <a name="to-test-the-visualizer"></a>시각화 도우미를 테스트하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyTestConsole** 선택 **시작 프로젝트로 설정** 바로 가기 메뉴.  
  
2.  에 **디버그** 메뉴 선택 **시작**합니다.  
  
     콘솔 응용 프로그램을 시작 하 고 시각화 도우미가 나타나고 "Hello, World" 문자열을 표시  
  
 이로써 첫 번째 시각화 도우미를 빌드하고 테스트했습니다.  
  
 시각화 도우미를 테스트 환경에서 호출하는 대신 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 사용하려면 이를 설치해야 합니다. 자세한 내용은 참조 [하는 방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)합니다.  
  
## <a name="create-a-visualizer-using-the-visualizer-item-template"></a>시각화 도우미 항목 템플릿을 사용 하 여 시각화 만들기  
 지금까지이 연습에서는 방법을 살펴보았습니다 시각화 도우미를 수동으로 만들어야 합니다. 이 작업은 학습 연습으로 수행 되었습니다. 보다 쉽게 만들 수 없는 간단한 시각화 도우미의 작동 원리를 파악 했으므로: 시각화 도우미 항목 템플릿을 사용 합니다.  
  
 첫째, 새 클래스 라이브러리 프로젝트를 만들 해야 할 수도 있습니다.  
  
#### <a name="to-create-a-new-class-library"></a>새 클래스 라이브러리를 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로 만들기 > 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 **Visual C#**선택, **.NET 표준**합니다.  
  
3.  가운데 창에서 선택 **클래스 라이브러리**합니다.   
  
4.  에 **이름** MySecondVisualizer 같은 클래스 라이브러리에 대 한 적절 한 이름을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
 이제 시각화 도우미 항목을 추가할 수 있습니다.  
  
#### <a name="to-add-a-visualizer-item"></a>시각화 도우미 항목을 추가 하려면  
  
1.  **솔루션 탐색기**, MySecondVisualizer를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 선택 **추가** 클릭 하 고 **새 항목**합니다.  
  
3.  에 **새 항목 추가** 대화 상자의 **Visual C# 항목**선택, **디버거 시각화 도우미**합니다.  
  
4.  에 **이름** SecondVisualizer.cs 등의 적절 한 이름을 입력 합니다.  
  
5.  **추가**를 클릭합니다.  
  
 즉, 모두 완료 되었습니다. 파일 SecondVisualizer.cs와 템플릿을 자동으로 추가 하는 코드를 확인 하십시오. 계속 진행 하 고 코드를 시험해 합니다. 수 발전 하 고 기본 사항을 배웠으므로 자신만의 더 복잡 하 고 유용한 시각화를 만들기.  
  
## <a name="see-also"></a>참고 항목  
 [시각화 도우미 아키텍처](../debugger/visualizer-architecture.md)   
 [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)   
 [Create Custom Visualizers of Data](../debugger/create-custom-visualizers-of-data.md)(데이터의 사용자 지정 시각화 도우미 만들기)
