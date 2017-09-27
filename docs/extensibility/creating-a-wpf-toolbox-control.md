---
title: "WPF 도구 상자 컨트롤 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox control
- toolbox
- wpf
ms.assetid: 9cc34db9-b0d1-4951-a02f-7537fbbb51ad
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 40196a61c1fdc1dd7f2cf7d75e5fa65fb0580160
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="creating-a-wpf-toolbox-control"></a>WPF 도구 상자 컨트롤 만들기
WPF (Windows Presentation Framework) 도구 상자 컨트롤 템플릿을 사용 하는 자동으로 추가 하는 WPF 컨트롤을 만들 수는 **도구 상자** 확장 기능이 설치 됩니다. 이 항목에서는 서식 파일 만들기를 사용 하는 방법을 보여 줍니다.는 **도구 상자** 컨트롤을 다른 사용자에 게 배포할 수 있습니다.  
  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-wpf-toolbox-control"></a>WPF 도구 상자 컨트롤 만들기  
  
#### <a name="create-an-extension-with-a-wpf-toolbox-control"></a>WPF 도구 상자 컨트롤 확장 만들기  
  
1.  라는 VSIX 프로젝트 `MyToolboxControl`합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C# / 확장성**합니다.  
  
2.  프로젝트를 열 때 추가 된 **WPF 도구 상자 컨트롤** 라는 항목 템플릿을 `MyToolboxControl`합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **WPF 도구 상자 컨트롤**합니다. 에 **이름** 창의 맨 아래에 필드에서 명령 파일 이름을 변경한 `MyToolboxControl.cs`합니다.  
  
     솔루션은 이제 사용자 정의 컨트롤을 포함 한 `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> 컨트롤을 추가 하는 **도구 상자**, 및 **Microsoft.VisualStudio.ToolboxControl** 에 대 한 VSIX 매니페스트의 자산 항목  배포 합니다.  
  
#### <a name="to-create-the-control-ui"></a>UI 컨트롤을 만들려면  
  
1.  MyToolboxControl.xaml 디자이너에서 엽니다.  
  
     디자이너에 표시 된는 <xref:System.Windows.Controls.Grid> 제어를 포함 하는 <xref:System.Windows.Controls.Button> 제어 합니다.  
  
2.  격자 레이아웃을 정렬 합니다. 선택 하는 경우는 <xref:System.Windows.Controls.Grid> 파란색 컨트롤 막대가 모눈의 왼쪽된 위 가장자리에 표시를 제어 합니다. 막대를 클릭 하 여 표에 행과 열을 추가할 수 있습니다.  
  
3.  눈금에 자식 컨트롤을 추가 합니다. 자식 컨트롤에서 끌어서 배치할 수 있습니다는 **도구 상자** 하거나 설정 하는 눈금의 섹션에 해당 `Grid.Row` 및 `Grid.Column` XAML의 특성입니다. 다음 예제에서는 그리드 및 단추를 두 번째 행의 맨 위 행에 두 개의 레이블을 추가합니다.  
  
    ```xaml  
    <Grid>  
        <Label Grid.Row="0" Grid.Column="0" Name="label1" />  
        <Label Grid.Row="0" Grid.Column="1" Name="label2" />  
        <Button Name="button1" Click="button1_Click" Grid.Row="1" Grid.ColumnSpan="2" />  
    </Grid>  
    ```  
  
## <a name="renaming-the-control"></a>컨트롤 이름 바꾸기  
 기본적으로 컨트롤에 표시 됩니다는 **도구 상자** 으로 **MyToolboxControl** 이라는 그룹에 **MyToolboxControl.MyToolboxControl**합니다. 이러한 MyToolboxControl.xaml.cs 파일이 이름을 변경할 수 있습니다.  
  
1.  코드 뷰에서 MyToolboxControl.xaml.cs를 엽니다.  
  
2.  MyToolboxControl 클래스를 찾아 이름을 TestControl로 변경 합니다. (이 작업을 수행 하는 가장 빠른 방법은 되는 클래스의 이름을 바꾸려면 다음을 선택 **이름 바꾸기** 상황에 맞는 메뉴에서 단계를 완료 합니다. (에 대 한 자세한 내용은 **이름 바꾸기** 명령에서 참조 [이름 바꾸기 리팩터링 (C#)](../csharp-ide/rename-refactoring-csharp.md).)  
  
3.  이동 하는 `ProvideToolboxControl` 첫 번째 매개 변수의 값을 변경 하 고 특성 **테스트**합니다. 에 컨트롤을 포함할 그룹의 이름에서 **도구 상자**합니다.  
  
     결과 코드는 다음과 같이 표시 됩니다.  
  
    ```csharp  
    [ProvideToolboxControl("Test", true)]  
    public partial class TestControl : UserControl  
    {  
        public TestControl()  
        {  
            InitializeComponent();  
        }  
    }  
    ```  
  
## <a name="building-testing-and-deployment"></a>빌드, 테스트 및 배포  
 컨트롤에 설치 된 프로젝트를 디버깅할 때 찾아야는 **도구 상자** Visual Studio의 실험적 인스턴스.  
  
#### <a name="to-build-and-test-the-control"></a>컨트롤을 빌드하고 테스트하려면  
  
1.  프로젝트를 다시 작성 하 고 디버깅을 시작 합니다.  
  
2.  Visual Studio의 새 인스턴스에서 WPF 응용 프로그램 프로젝트를 만듭니다. XAML 디자이너가 열려 있는지 확인 합니다.  
  
3.  **도구 상자** 에서 컨트롤을 찾아 디자인 화면으로 끕니다.  
  
4.  WPF 응용 프로그램 디버깅을 시작 합니다.  
  
5.  컨트롤이 표시 되 고 있는지 확인 하십시오.  
  
#### <a name="to-deploy-the-control"></a>컨트롤을 배포하려면  
  
1.  테스트 된 프로젝트를 빌드한 후에 프로젝트의 \bin\debug\ 폴더에.vsix 파일을 찾을 수 있습니다.  
  
2.  .Vsix 파일을 두 번 클릭 하 고 설치 절차를 수행 하 여 로컬 컴퓨터에 설치할 수 있습니다. 컨트롤을 제거 하려면로 이동 **도구 / 확장명 및 업데이트** 및 컨트롤 확장에 대 한 확인 한 후 클릭 **제거**합니다.  
  
3.  네트워크 또는 웹 사이트에 .vsix 파일을 업로드합니다.  
  
     파일을 업로드 하는 경우는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트를 다른 사용자가 사용할 수 **도구 / 확장명 및 업데이트** 온라인 컨트롤을 찾아 설치할 수 있도록 Visual Studio에서 합니다.
