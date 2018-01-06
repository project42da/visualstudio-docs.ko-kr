---
title: "연습: Visual Basic에서 시각화 도우미 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: c93bf5a1-3e5e-422f-894e-bd72c9bc1b57
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7ad673736334daec79860b9832a056c17781a082
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-writing-a-visualizer-in-visual-basic"></a>연습: Visual Basic에서 시각화 도우미 작성
이 연습에서는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]을 사용하여 간단한 시각화 도우미를 작성하는 방법을 보여 줍니다. 이 연습에서 만들 시각화 도우미는 Windows Forms 메시지 상자를 사용하여 문자열의 내용을 표시합니다. 이 간단한 문자열 시각화 도우미는 프로젝트에 더 유용하게 사용할 수 있는 다른 형식에 대한 시각화 도우미를 만드는 방법을 보여 주는 기본 예제입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경 하려면로 이동 된 **도구** 메뉴 선택 **가져오기 및 내보내기** 합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 시각화 도우미 코드는 디버거에서 읽을 DLL에 배치해야 합니다. 따라서 가장 먼저 할 일은 DLL의 클래스 라이브러리 프로젝트를 만드는 것입니다.  
  
## <a name="create-and-prepare-a-class-library-project"></a>클래스 라이브러리 프로젝트 만들기 및 준비  
  
#### <a name="to-create-a-class-library-project"></a>클래스 라이브러리 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로** 클릭 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 **프로젝트 형식**s, 클릭 **Visual Basic**합니다.  
  
3.  에 **템플릿** 상자 **클래스 라이브러리**합니다.  
  
4.  에 **이름** 상자와 같은 클래스 라이브러리에 대 한 적절 한 이름을 입력 합니다 **MyFirstVisualizer**합니다.  
  
5.  **확인**을 클릭합니다.  
  
 클래스 라이브러리를 만든 후에는 Microsoft.VisualStudio.DebuggerVisualizers.DLL에 대한 참조를 추가하여 여기에서 정의한 클래스를 사용할 수 있도록 해야 합니다. 그 전에 프로젝트에 의미 있는 이름을 부여해야 합니다.  
  
#### <a name="to-rename-class1vb-and-add-microsoftvisualstudiodebuggervisualizers"></a>Class1.vb의 이름을 바꾸고 Microsoft.VisualStudio.DebuggerVisualizers를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Class1.vb**, 바로 가기 메뉴를 클릭 하 고 **이름 바꾸기**합니다.  
  
2.  이름을 Class1.vb에서 DebuggerSide.vb 같은 의미 있는 이름으로 변경합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 새 파일 이름과 일치하도록 DebuggerSide.vb의 클래스 선언이 자동으로 변경됩니다.  
  
3.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **My First Visualizer**, 바로 가기 메뉴를 클릭 하 고 **참조 추가**합니다.  
  
4.  에 **참조 추가** 대화 상자의 **.NET** 탭에서 Microsoft.VisualStudio.DebuggerVisualizers.DLL을 클릭 합니다.  
  
5.  **확인**을 클릭합니다.  
  
6.  DebuggerSide.vb에서 다음 문을 `Imports` 문에 추가합니다.  
  
    ```  
    Imports Microsoft.VisualStudio.DebuggerVisualizers  
    ```  
  
## <a name="add-the-debugger-side-code"></a>디버거 쪽 코드 추가  
 이제 디버거 쪽 코드를 만들 준비가 되었습니다. 이는 시각화하려는 정보를 표시하기 위해 디버거 내에서 실행되는 코드입니다. 먼저 `DebuggerSide` 개체의 선언을 변경하여 `DialogDebuggerVisualizer` 기본 클래스에서 상속하도록 해야 합니다.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>DialogDebuggerVisualizer에서 상속하려면  
  
1.  DebuggerSide.vb에서 다음 코드 줄로 이동합니다.  
  
    ```  
    Public Class DebuggerSide  
    ```  
  
2.  코드를 다음과 같이 편집합니다.  
  
    ```  
    Public Class DebuggerSide  
    Inherits DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer`에는 재정의해야 할 추상 메서드 하나(`Show`)가 있습니다.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>DialogDebuggerVisualizer.Show 메서드를 재정의하려면  
  
-   `public class DebuggerSide`에서 다음 메서드를 추가합니다.  
  
    ```  
    Protected Overrides Sub Show(ByVal windowService As Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService, ByVal objectProvider As Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider)  
  
        End Sub  
    ```  
  
 `Show` 메서드에는 시각화 도우미 대화 상자나 기타 사용자 인터페이스를 실제로 만들고 디버거에서 시각화 도우미로 전달된 정보를 표시하는 코드가 들어 있습니다. 대화 상자를 만들고 정보를 표시하는 코드를 추가해야 합니다. 이 연습에서는 Windows Forms 메시지 상자를 사용하여 이 작업을 수행합니다. 먼저 `Imports`에 대한 참조와 <xref:System.Windows.Forms> 문을 추가해야 합니다.  
  
#### <a name="to-add-systemwindowsforms"></a>System.Windows.Forms을 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 바로 가기 메뉴를 클릭 하 고 **참조 추가**합니다.  
  
2.  에 **참조 추가** 대화 상자의 **.NET** 탭을 클릭 **System.Windows.Forms**합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  DebuggerSide.cs에서 다음 문을 `Imports` 문에 추가합니다.  
  
    ```  
    Imports System.Windows.Forms  
    ```  
  
## <a name="create-your-visualizers-user-interface"></a>시각화 도우미의 사용자 인터페이스 만들기  
 이제 시각화 도우미의 사용자 인터페이스를 만들고 표시하는 코드를 추가합니다. 이 연습에서는 처음으로 시각화 도우미를 만드는 것이므로 사용자 인터페이스를 간단하게 유지하고 메시지 상자를 사용합니다.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>시각화 도우미 출력을 대화 상자에 표시하려면  
  
1.  `Show` 메서드에 다음 코드 줄을 추가합니다.  
  
    ```  
    MessageBox.Show(objectProvider.GetObject().ToString())  
    ```  
  
     이 예제 코드에는 오류 처리 기능이 포함되어 있지 않습니다. 실제 시각화 도우미나 기타 유형의 응용 프로그램을 만들 때는 오류 처리 기능을 포함해야 합니다.  
  
2.  에 **빌드** 메뉴를 클릭 하 여 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
## <a name="add-the-necessary-attribute"></a>필수 특성 추가  
 이제 디버거(debugger) 쪽 코드를 모두 작성했습니다. 그러나 여기에서 한 단계를 추가로 수행해야 합니다. 시각화 도우미를 구성하는 클래스 컬렉션을 디버기 쪽에 알리는 특성이 필요합니다.  
  
#### <a name="to-add-the-debugee-side-code"></a>디버기 쪽 코드를 추가하려면  
  
1.  DebuggerSide.vb의 `Imports` 문과 `namespace MyFirstVisualizer` 문 사이에 다음 특성 코드를 추가합니다.  
  
    ```  
    <Assembly: System.Diagnostics.DebuggerVisualizer(GetType(MyFirstVisualizer.DebuggerSide), GetType(VisualizerObjectSource), Target:=GetType(System.String), Description:="My First Visualizer")>  
    ```  
  
2.  에 **빌드** 메뉴를 클릭 하 여 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
## <a name="create-a-test-harness"></a>테스트 도구 만들기  
 이제 첫 번째 시각화 도우미가 완성되었습니다. 각 단계를 올바르게 수행했으면 시각화 도우미를 빌드하고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치할 수 있을 것입니다. 그러나 시각화 도우미를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치하기 전에 이를 테스트하여 올바르게 실행되는지 확인해야 합니다. 이제 시각화 도우미를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 설치하지 않고 실행하는 테스트 환경을 만듭니다.  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>시각화 도우미를 표시하기 위한 테스트 메서드를 추가하려면  
  
1.  `public DebuggerSide` 클래스에 다음 메서드를 추가합니다.  
  
    ```  
    Shared Public Sub TestShowVisualizer(ByVal objectToVisualize As Object)  
        Dim visualizerHost As New VisualizerDevelopmentHost(objectToVisualize, GetType(DebuggerSide))  
    visualizerHost.ShowVisualizer()  
    End Sub  
    ```  
  
2.  에 **빌드** 메뉴를 클릭 하 여 **MyFirstVisualizer 빌드**합니다. 프로젝트가 성공적으로 빌드되어야 합니다. 빌드 오류가 발생하면 계속 진행하기 전에 이를 수정합니다.  
  
 이제 시각화 도우미 DLL을 호출하기 위한 실행 파일 프로젝트를 만들어야 합니다. 작업을 간소화하기 위해 콘솔 응용 프로그램 프로젝트를 사용합니다.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>솔루션에 콘솔 응용 프로그램 프로젝트를 추가하려면  
  
1.  에 **파일** 메뉴를 클릭 하 여 **추가**, 클릭 하 고 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트 추가** 대화 상자는 **템플릿** 상자 **콘솔 응용 프로그램**합니다.  
  
3.  에 **이름** 상자와 같은 콘솔 응용 프로그램에 대 한 의미 있는 이름을 입력 합니다 **MyTestConsole**합니다.  
  
4.  **확인**을 클릭합니다.  
  
 이제 MyTestConsole에서 MyFirstVisualizer를 호출하는 데 필요한 참조를 추가해야 합니다.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>MyTestConsole에 필요한 참조를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyTestConsole**, 바로 가기 메뉴를 클릭 하 고 **참조 추가**합니다.  
  
2.  에 **참조 추가** 대화 상자의 **.NET** 탭에서 Microsoft.VisualStudio.DebuggerVisualizers를 클릭 합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **MyTestConsole**, 클릭 하 고 **참조 추가** 다시 합니다.  
  
5.  에 **참조 추가** 대화 상자를 클릭는 **프로젝트** 탭 하 고 MyFirstVisualizer를 선택 합니다.  
  
6.  **확인**을 클릭합니다.  
  
## <a name="finish-your-test-harness-and-test-your-visualizer"></a>테스트 도구 끝내기 및 시각화 도우미 테스트  
 이제 테스트 환경을 끝내기 위한 코드를 추가합니다.  
  
#### <a name="to-add-code-to-mytestconsole"></a>MyTestConsole에 코드를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Program.vb**, 바로 가기 메뉴를 클릭 하 고 **이름 바꾸기**합니다.  
  
2.  와 같은 적절 한, Module1.vb에서 이름을 편집 **TestConsole.vb**합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 새 파일 이름과 일치하도록 TestConsole.vb의 클래스 선언이 자동으로 변경된다는 점에 유의해야 합니다.  
  
3.  TestConsole에. vb, 다음 추가 `Imports` 문:  
  
    ```  
    Imports MyFirstVisualizer  
    ```  
  
4.  `Main` 메서드에 다음 코드를 추가합니다.  
  
    ```  
    Dim myString As String = "Hello, World"  
    DebuggerSide.TestShowVisualizer(myString)  
    ```  
  
 이제 첫 번째 시각화 도우미를 테스트할 준비가 되었습니다.  
  
#### <a name="to-test-the-visualizer"></a>시각화 도우미를 테스트하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyTestConsole**, 바로 가기 메뉴를 클릭 하 고 **시작 프로젝트로 설정**합니다.  
  
2.  에 **디버그** 메뉴를 클릭 하 여 **시작**합니다.  
  
     콘솔 응용 프로그램이 시작됩니다. 시각화 도우미가 나타나고 "Hello, World."라는 문자열이 표시됩니다.  
  
 이로써 첫 번째 시각화 도우미를 빌드하고 테스트했습니다.  
  
 시각화 도우미를 테스트 환경에서 호출하는 대신 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 사용하려면 이를 설치해야 합니다. 자세한 내용은 참조 [하는 방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시각화 도우미 아키텍처](../debugger/visualizer-architecture.md)   
 [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)   
 [Create Custom Visualizers of Data](../debugger/create-custom-visualizers-of-data.md)(데이터의 사용자 지정 시각화 도우미 만들기)