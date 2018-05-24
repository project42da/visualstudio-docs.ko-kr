---
title: '연습: 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기, 2 부 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], creating template wizards
- SharePoint project items, creating template wizards
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0aa938d41540229d6cd91598968f104b3fa3a7be
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2"></a>연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부
  사용자 지정 형식의 SharePoint 프로젝트 항목을 정의 하 고 Visual Studio에서 프로젝트 템플릿을 사용 하 여 연결 하는 마법사를 제공 수도 있습니다. 서식 파일 프로젝트 항목이 포함 된 새 프로젝트를 만들려면 사용할 때 사용자 로부터 정보를 수집 하는 마법사를 사용할 수 있습니다. 수집 하는 정보는 프로젝트 항목을 초기화 데 사용할 수 있습니다.  
  
 이 연습에 설명 된 사이트 열 프로젝트 템플릿에 마법사를 추가 합니다 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)합니다. 사용자가 사이트 열 프로젝트를 만들 때 마법사는 사이트 열 (예: 기본 형식 및 그룹)에 대 한 정보를 수집 하 고이 정보를 새 프로젝트에서 Elements.xml 파일 추가.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트 템플릿에 연결 되어 있으므로 사용자 지정 SharePoint 프로젝트 항목 형식에 대 한 마법사 만들기  
  
-   사용자 지정 마법사 Visual Studio에서 SharePoint 프로젝트에 대 한 기본 제공 마법사 유사한 UI를 정의 합니다.  
  
-   두 개의 만들기 *SharePoint 명령* 마법사를 실행 하는 동안 로컬 SharePoint 사이트를 호출 하는 데 사용 되는 합니다. SharePoint 명령은 SharePoint 서버 개체 모델의 Api를 호출 합니다. Visual Studio 확장 프로그램에서 사용할 수 있는 메서드입니다. 자세한 내용은 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
-   대체 가능 매개 변수를 사용 하 여 마법사에서 수집한 데이터가 포함 된 SharePoint 프로젝트 파일을 초기화 합니다.  
  
-   각 새 사이트 열 프로젝트 개체의 새.snk 파일을 만듭니다. 이 파일은 프로젝트에서 SharePoint 솔루션 어셈블리를 전역 어셈블리 캐시에 배포할 수 있도록 출력에 서명 하려면 사용 합니다.  
  
-   디버깅 하 고 마법사를 테스트 합니다.  
  
> [!NOTE]  
> 샘플 워크플로의 계열에 대 한 참조 [SharePoint 워크플로 샘플](https://docs.microsoft.com/sharepoint/dev/general-development/sharepoint-workflow-samples)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 수행 하려면 먼저 만들어야 합니다 SiteColumnProjectItem 솔루션을 완료 하 여 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)합니다.  
  
 또한이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 Windows, SharePoint 및 Visual Studio의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio SDK입니다. 이 연습에서는 **VSIX 프로젝트** 프로젝트 항목을 배포 하려면 VSIX 패키지를 만드는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   Visual Studio에서 프로젝트 및 항목 템플릿에 대 한 마법사를 제공 합니다. 자세한 내용은 참조 [하는 방법: 프로젝트 템플릿이 함께 제공 마법사 사용](../extensibility/how-to-use-wizards-with-project-templates.md) 및 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스입니다.  
  
-   Sharepoint에서 사이트 열입니다. 자세한 내용은 참조 [열](http://go.microsoft.com/fwlink/?LinkId=183547)합니다.  
  
##  <a name="wizardcomponents"></a> 마법사 구성 요소 이해  
 이 연습에 설명 된 마법사에는 몇 가지 구성 요소를 포함 합니다. 다음 표에서 이러한 구성 요소를 설명합니다.  
  
|구성 요소|설명|  
|---------------|-----------------|  
|마법사 구현|이것은 라는 클래스를 `SiteColumnProjectWizard`를 구현 하는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스입니다. 이 인터페이스는 Visual Studio에서 마법사를 시작 하 고 완료 되 면 실행 하는 경우 마법사 중 특정 시간에 호출 하는 메서드를 정의 합니다.|  
|마법사 UI|이 라는 WPF 기반 창을 `WizardWindow`합니다. 이 창에 라는 두 개의 사용자 정의 컨트롤 `Page1` 및 `Page2`합니다. 이러한 사용자 정의 컨트롤 마법사의 두 페이지를 나타냅니다.<br /><br /> 이 연습에서는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 마법사 구현 방식의 마법사 UI가 표시 됩니다.|  
|데이터 모델 마법사|이 클래스는 명명 된 중간 클래스 `SiteColumnWizardModel`, 마법사 UI 및 마법사 구현 사이의 계층을 제공 하는 합니다. 이 샘플이이 클래스를 사용 하 여 추상 마법사 구현 및 다른; 마법사 UI 도움말 이 클래스는 모든 마법사의 필수 구성 요소는 아닙니다.<br /><br /> 이 연습에서는 마법사 구현이 전달는 `SiteColumnWizardModel` 마법사 UI를 표시 하는 경우 마법사 창에 개체를 합니다. 마법사 UI이이 개체의 메서드를 사용 하 여 ui에서 컨트롤의 값을 저장 하 고 입력된 사이트 URL이 올바른지 확인 하는 등 작업을 수행 합니다. 마법사 구현이 사용 하 여 사용자가 마법사를 완료는 `SiteColumnWizardModel` UI의 최종 상태를 확인 하는 개체입니다.|  
|프로젝트 서명 관리자|이 라는 도우미 클래스를 `ProjectSigningManager`, 인스턴스마다 새 프로젝트에에서 새 key.snk 파일을 만드는 마법사 구현에서 사용 되는 합니다.|  
|SharePoint 명령|이 마법사 데이터 모델 마법사를 실행 하는 동안 로컬 SharePoint 사이트를 호출 하기 위해 사용 되는 메서드입니다. SharePoint 명령은.NET Framework 3.5를 대상 해야 하기 때문에이 명령은 마법사 코드의 나머지 부분 보다 다른 어셈블리에서 구현 됩니다.|  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 몇 가지 프로젝트에서 만든 SiteColumnProjectItem 솔루션에 추가할 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md):  
  
-   WPF 프로젝트입니다. 구현 합니다는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를이 프로젝트에서 마법사 UI를 정의 합니다.  
  
-   SharePoint 명령을 정의 하는 클래스 라이브러리 프로젝트. 이 프로젝트는 the.NET Framework 3.5를 대상 해야 합니다.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-wpf-project"></a>WPF 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SiteColumnProjectItem** 솔루션 노드를 선택 **추가**를 선택한 후 **새프로젝트**.  
  
3.  맨 위에 있는 **새 프로젝트 추가** 대화 상자에서 다음 사항을 확인 **.NET Framework 4.5** 버전의.NET Framework의 목록에서 선택 됩니다.  
  
4.  확장 된 **Visual C#** 노드 또는 **Visual Basic** 노드를 선택 하 고는 **Windows** 노드.  
  
5.  프로젝트 템플릿 목록에서 선택 **WPF 사용자 정의 컨트롤 라이브러리**, 프로젝트 이름을 **ProjectTemplateWizard**를 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **ProjectTemplateWizard** 프로젝트를 솔루션 기본 usercontrol1.xaml이 파일을 엽니다.  
  
6.  프로젝트에서 usercontrol1.xaml이 파일을 삭제 합니다.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>SharePoint 명령은 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**SiteColumnProjectItem 솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  맨 위에 있는 **새 프로젝트 추가** 대화 상자에서 선택 **.NET Framework 3.5** 버전의.NET Framework의 목록에 있습니다.  
  
3.  확장 된 **Visual C#** 노드 또는 **Visual Basic** 노드를 선택한 후는 **Windows** 노드.  
  
4.  선택 된 **클래스 라이브러리** 서식 파일 프로젝트에서 프로젝트 이름을 **SharePointCommands**, 선택한 후는 **확인** 단추 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **SharePointCommands** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-projects"></a>프로젝트 구성  
 마법사를 만들기 전에 일부 코드 파일 및 프로젝트에 어셈블리 참조를 추가 해야 합니다.  
  
#### <a name="to-configure-the-wizard-project"></a>마법사 프로젝트를 구성 하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **ProjectTemplateWizard** 프로젝트 노드를 선택한 후 **속성**합니다.  
  
2.  에 **프로젝트 디자이너**, 선택는 **응용 프로그램** Visual C# 프로젝트에 대 한 탭 또는 **컴파일** Visual Basic 프로젝트에 대 한 탭 합니다.  
  
3.  대상 프레임 워크가.NET Framework 4.5,.NET Framework 4.5 클라이언트 프로필 아님로 설정 되어 있는지 확인 합니다.  
  
     자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.  
  
4.  에 대 한 바로 가기 메뉴를 열고는 **ProjectTemplateWizard** 프로젝트 **추가**를 선택한 후 **새 항목**합니다.  
  
5.  선택 된 **창 (WPF)** 항목, 항목 이름을 **WizardWindow**, 선택한 후는 **추가** 단추 합니다.  
  
6.  두 개의 추가 **사용자 정의 컨트롤 (WPF)** 항목을 프로젝트에 이름을 지정 하 고 **1 페이지** 및 **페이지 2**합니다.  
  
7.  4 개의 코드 파일을 프로젝트에 추가 하 고 다음의 이름을 지정:  
  
    -   SiteColumnProjectWizard  
  
    -   SiteColumnWizardModel  
  
    -   ProjectSigningManager  
  
    -   CommandIds  
  
8.  에 대 한 바로 가기 메뉴를 열고는 **ProjectTemplateWizard** 프로젝트 노드를 선택한 후 **참조 추가**합니다.  
  
9. 확장의 **어셈블리** 노드를 선택는 **확장** 노드와 다음 어셈블리 옆의 확인란을 선택 합니다.  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
10. 선택 된 **확인** 프로젝트에 어셈블리를 추가 하는 단추입니다.  
  
11. **솔루션 탐색기**아래는 **참조** 에 대 한 폴더는 **ProjectTemplateWizard** 프로젝트 **EnvDTE**합니다.  
  
12. 에 **속성** 창의 값을 변경는 **Interop 형식 포함** 속성을 **False**합니다.  
  
13. Visual Basic 프로젝트를 개발 하는 경우 ProjectTemplateWizard 네임 스페이스를 프로젝트에 사용 하 여 가져올는 **프로젝트 디자이너**합니다.  
  
     자세한 내용은 참조 [하는 방법: 추가 또는 가져온 네임 스페이스 제거 &#40;Visual Basic&#41;](../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md)합니다.  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>SharePointCommands 프로젝트를 구성 하려면  
  
1.  **솔루션 탐색기**, 선택는 **SharePointCommands** 프로젝트 노드.  
  
2.  메뉴 모음에서 **프로젝트**, **기존 항목 추가**합니다.  
  
3.  에 **기존 항목 추가** 대화 상자, ProjectTemplateWizard 프로젝트에 대 한 코드 파일이 포함 된 폴더를 찾아 선택 합니다는 **CommandIds** 코드 파일.  
  
4.  옆에 있는 화살표를 선택는 **추가** 단추를 선택한 후는 **링크로 추가** 나타나는 메뉴에서 옵션입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 코드 파일을 추가 하는 **SharePointCommands** 링크로 프로젝트입니다. 코드 파일에는 **ProjectTemplateWizard** 프로젝트 이지만 파일의 코드에도 컴파일된는 **SharePointCommands** 프로젝트.  
  
5.  에 **SharePointCommands** 프로젝트에서 명령을 라고 하는 다른 코드 파일을 추가 합니다.  
  
6.  SharePointCommands 프로젝트를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **참조 추가**합니다.  
  
7.  확장의 **어셈블리** 노드를 선택는 **확장** 노드와 다음 어셈블리 옆의 확인란을 선택 합니다.  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
8.  선택 된 **확인** 프로젝트에 어셈블리를 추가 하는 단추입니다.  
  
## <a name="creating-the-wizard-model-signing-manager-and-sharepoint-command-ids"></a>관리자 및 SharePoint 명령 Id 서명 마법사 모델 만들기  
 이 샘플에서 다음 구성 요소를 구현 하 ProjectTemplateWizard 프로젝트에 코드를 추가 합니다.  
  
-   SharePoint 명령 Id입니다. 이러한 문자열에는 마법사를 사용 하는 SharePoint 명령 식별 합니다. 이 연습의 뒷부분에서 명령을 구현 하려면 SharePointCommands 프로젝트에 코드를 추가 합니다.  
  
-   마법사 데이터 모델입니다.  
  
-   프로젝트의 서명 관리자입니다.  
  
 이러한 구성 요소에 대 한 자세한 내용은 참조 [마법사 구성 요소 이해](#wizardcomponents)합니다.  
  
#### <a name="to-define-the-sharepoint-command-ids"></a>SharePoint 명령 Id를 정의 하려면  
  
1.  ProjectTemplateWizard 프로젝트에서 CommandIds 코드 파일을 연 후이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/commandids.cs#5)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/commandids.vb#5)]  
  
#### <a name="to-create-the-wizard-model"></a>마법사 모델을 만들려면  
  
1.  SiteColumnWizardModel 코드 파일을 열고이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.vb#6)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.cs#6)]  
  
#### <a name="to-create-the-project-signing-manager"></a>프로젝트 서명 관리자를 만들려면  
  
1.  ProjectSigningManager 코드 파일을 연 후이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.vb#8)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.cs#8)]  
  
## <a name="creating-the-wizard-ui"></a>마법사 UI 만들기  
 마법사 창 및 마법사 페이지에 대 한 UI를 제공 하는 두 개의 사용자 정의 컨트롤의 UI를 정의 하는 XAML을 추가 하 고 창 및 사용자 정의 컨트롤의 동작을 정의 하는 코드를 추가 합니다. 마법사를 만들면 Visual Studio에서 SharePoint 프로젝트에 대 한 기본 제공 마법사와 유사 합니다.  
  
> [!NOTE]  
>  다음 단계에서는 프로젝트에 프로젝트에 XAML 또는 코드를 추가 하면 컴파일 오류가 발생 해야 합니다. 이러한 오류는 사라집니다 이후 단계에서 코드를 추가 합니다.  
  
#### <a name="to-create-the-wizard-window-ui"></a>마법사 창을 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트에서 WizardWindow.xaml 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고** 디자이너에서 창을 엽니다.  
  
2.  디자이너의 XAML 뷰에서 XAML을 현재 다음 XAML로 바꿉니다. XAML 정의 제목을 포함 하는 UI는 <xref:System.Windows.Controls.Grid> 마법사 페이지를 포함 하 고 탐색 창의 맨 아래에 단추가 있습니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#10](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml#10)]  
  
    > [!NOTE]  
    >  이 XAML에서 생성 된 창에서 파생 되는 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> 기본 클래스입니다. Visual Studio에 사용자 지정 WPF 대화 상자를 추가 하는 경우에 다른 Visual Studio 대화 상자와 일관성 있는 스타일 하 고 발생할 수 있는 모달 대화 상자 문제를 방지 하기 위해이 클래스에서 대화 상자를 파생 하는 것이 좋습니다. 자세한 내용은 참조 [만들기 및 모달 대화 상자 관리](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes)합니다.  
  
3.  Visual Basic 프로젝트를 개발 하는 경우 제거는 `ProjectTemplateWizard` 에서 네임 스페이스는 `WizardWindow` 클래스 이름에는 `x:Class` 특성은 `Window` 요소입니다. XAML의 첫 번째 줄에 있는이 요소가입니다. 완료 되 면 첫 번째 줄은 다음 예제에서는 같습니다.  
  
    ```xml  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml 파일에 대 한 코드 숨김 파일을 엽니다.  
  
5.  제외 하 고이 파일의 내용을 바꿉니다는 `using` 선언을 다음 코드로 파일 맨 위에 있는 합니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.vb#4)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.cs#4)]  
  
#### <a name="to-create-the-first-wizard-page-ui"></a>첫 번째 마법사 페이지 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트에서 Page1.xaml 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고** 디자이너에서 사용자 컨트롤을 엽니다.  
  
2.  디자이너의 XAML 뷰에서 XAML을 현재 다음 XAML로 바꿉니다. XAML은 사용자는 원하는 디버깅에 사용할 로컬 사이트의 URL을 입력할 수 있는 입력란을 포함 하는 UI를 정의 합니다. UI에 옵션 단추는 사용자가 프로젝트의 샌드박스 인지 지정할 수 포함 되어 있습니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#11](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page1.xaml#11)]  
  
3.  Visual Basic 프로젝트를 개발 하는 경우 제거는 `ProjectTemplateWizard` 에서 네임 스페이스는 `Page1` 클래스 이름에는 `x:Class` 특성은 `UserControl` 요소입니다. XAML의 첫 번째 줄에입니다. 완료 되 면 첫 번째 줄은 다음과 같습니다.  
  
    ```xml  
    <UserControl x:Class="Page1"  
    ```  
  
4.  제외 하 고 Page1.xaml 파일의 내용을 대체는 `using` 선언을 다음 코드로 파일 맨 위에 있는 합니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.cs#2)]  
  
#### <a name="to-create-the-second-wizard-page-ui"></a>두 번째 마법사 페이지 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트에서 Page2.xaml 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다.  
  
     사용자 정의 컨트롤이 디자이너에서 열립니다.  
  
2.  XAML 뷰에서 현재 XAML을 다음 XAML로 바꿉니다. XAML은 사이트 열, 갤러리에서 사이트 열을 표시 하는 기본 제공 또는 사용자 지정 그룹을 지정 하기 위한 콤보 상자 및 사이트 열 이름을 지정 하는 텍스트 상자가의 기본 형식을 선택 하기 위한 드롭 다운 목록을 포함 하는 UI를 정의 합니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#12](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page2.xaml#12)]  
  
3.  Visual Basic 프로젝트를 개발 하는 경우 제거는 `ProjectTemplateWizard` 에서 네임 스페이스는 `Page2` 클래스 이름에는 `x:Class` 특성은 `UserControl` 요소입니다. XAML의 첫 번째 줄에입니다. 완료 되 면 첫 번째 줄은 다음과 같습니다.  
  
    ```xml  
    <UserControl x:Class="Page2"  
    ```  
  
4.  내용을 대체 합니다 Page2.xaml 파일에 대 한 코드 숨김 파일을 제외 하 고는 `using` 선언을 다음 코드로 파일 맨 위에 있는 합니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.vb#3)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.cs#3)]  
  
## <a name="implementing-the-wizard"></a>마법사를 구현합니다.  
 마법사의 주요 기능을 구현 하 여 정의 된 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스입니다. 이 인터페이스는 Visual Studio에서 마법사를 시작 하 고 완료 되 면 실행 하는 경우 마법사 중 특정 시간에 호출 하는 메서드를 정의 합니다.  
  
#### <a name="to-implement-the-wizard"></a>마법사를 구현 하려면  
  
1.  ProjectTemplateWizard 프로젝트에서 SiteColumnProjectWizard 코드 파일을 엽니다.  
  
2.  이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.cs#7)]  
  
## <a name="creating-the-sharepoint-commands"></a>SharePoint 명령 만들기  
 SharePoint 서버 개체 모델을 호출 하는 두 개의 사용자 지정 명령을 만듭니다. 하나의 명령 마법사에 사용자를 입력 하는 사이트 URL이 유효한 지 확인 합니다. 다른 명령이 사용자가 자신의 새 사이트 열에 대 한 기준으로 사용 하도록 선택할 수 있도록 모든 필드 형식 지정 된 SharePoint 사이트에서 가져옵니다.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint 명령을 정의 하려면  
  
1.  에 **SharePointCommands** 프로젝트를 명령 코드 파일을 엽니다.  
  
2.  이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/sharepointcommands/commands.vb#9)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/sharepointcommands/commands.cs#9)]  
  
## <a name="checkpoint"></a>검사점  
 이 연습에서는 마법사에 대 한 모든 코드 프로젝트에 포함 되었습니다. 오류 없이 컴파일되는지 확인 하려면 프로젝트를 빌드하십시오.  
  
#### <a name="to-build-your-project"></a>프로젝트를 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## <a name="removing-the-keysnk-file-from-the-project-template"></a>프로젝트 템플릿에서 key.snk 파일을 제거합니다.  
 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md), 사용자가 만든 프로젝트 템플릿을 사이트 열 프로젝트 인스턴스마다 서명에 사용 되는 key.snk 파일을 포함 합니다. 이 key.snk 파일은 마법사에는 이제 각 프로젝트에 대 한 새 key.snk 파일을 생성 하기 때문에 더 이상 필요 합니다. 프로젝트 템플릿에서 key.snk 파일을 제거 하 고이 파일에 대 한 참조를 제거 합니다.  
  
#### <a name="to-remove-the-keysnk-file-from-the-project-template"></a>프로젝트 템플릿에서 key.snk 파일을 제거 하려면  
  
1.  **솔루션 탐색기**아래는 **SiteColumnProjectTemplate** 노드를에 대 한 바로 가기 메뉴를 열고는 **key.snk** 파일을 선택한 다음 선택 **삭제**.  
  
2.  나타나는 확인 대화 상자에서 선택 된 **확인** 단추입니다.  
  
3.  아래는 **SiteColumnProjectTemplate** 노드를 SiteColumnProjectTemplate.vstemplate 파일을 연 후 여기에서 다음 요소를 제거 합니다.  
  
    ```xml  
    <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
    ```  
  
4.  파일을 저장한 후 닫습니다.  
  
5.  아래는 **SiteColumnProjectTemplate** 노드를 ProjectTemplate.csproj 또는 ProjectTemplate.vbproj 파일을 연 후 다음을 제거 `PropertyGroup` 여기에서 요소입니다.  
  
    ```xml  
    <PropertyGroup>  
      <SignAssembly>true</SignAssembly>  
      <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
    </PropertyGroup>  
    ``` 
  
6.  다음 제거 `None` 요소입니다.  
  
    ```xml  
    <None Include="key.snk" />  
    ```  
  
7.  파일을 저장한 후 닫습니다.  
  
## <a name="associating-the-wizard-with-the-project-template"></a>마법사 프로젝트 템플릿을 사용 하 여 연결  
 마법사를 구현 했으므로는 마법사를 연결 해야는 **사이트 열** 서식 파일 프로젝트. 이 작업을 수행 하기 위해 완료 해야 하는 세 가지 절차가 있습니다.  
  
1.  강력한 이름의 마법사 어셈블리에 서명 합니다.  
  
2.  마법사 어셈블리에 대 한 공개 키를 토큰을 가져옵니다.  
  
3.  마법사 어셈블리에 대 한 참조에 대 한.vstemplate 파일에 추가 된 **사이트 열** 프로젝트 템플릿을 합니다.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>강력한 이름의 마법사 어셈블리에 서명 하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **ProjectTemplateWizard** 프로젝트를 선택한 후 **속성**합니다.  
  
2.  에 **서명** 탭을는 **어셈블리에 서명** 확인란 합니다.  
  
3.  에 **강력한 이름 키 파일 선택** 목록에서 선택  **\<새로 만들기 … >** 합니다.  
  
4.  에 **강력한 이름 키 만들기** 대화 상자 선택을 취소 새 키 파일에 대 한 이름을 입력 합니다는 **암호로 내 키 파일 보호** 확인란을 선택한 후는 **확인** 단추입니다.  
  
5.  에 대 한 바로 가기 메뉴를 열고는 **ProjectTemplateWizard** 프로젝트를 선택한 후 **빌드** ProjectTemplateWizard.dll 파일을 만들 수 있습니다.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>마법사 어셈블리에 대 한 공개 키 토큰 가져오려는  
  
1.  에 **시작 메뉴**, 선택 **모든 프로그램**, 선택 **Microsoft Visual Studio**, 선택 **Visual Studio Tools**, 선택 **개발자 명령 프롬프트**합니다.  
  
     Visual Studio 명령 프롬프트 창이 열립니다.  
  
2.  다음 명령을 실행 대체 *PathToWizardAssembly* 빌드된 ProjectTemplateWizard.dll 어셈블리 개발 컴퓨터에 ProjectTemplateWizard 프로젝트에 대 한 전체 경로:  
  
    ```cmd  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     ProjectTemplateWizard.dll 어셈블리에 대 한 공개 키 토큰은 Visual Studio 명령 프롬프트 창에 기록 됩니다.  
  
3.  Visual Studio 명령 프롬프트 창을 계속 열어둡니다. 다음 절차 중 공개 키 토큰이 필요 합니다.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>.Vstemplate 파일에 마법사 어셈블리에 대 한 참조를 추가 하려면  
  
1.  **솔루션 탐색기**를 확장 하 고는 **SiteColumnProjectTemplate** 프로젝트 노드 및 SiteColumnProjectTemplate.vstemplate 파일을 엽니다.  
  
2.  파일의 끝에 다음 추가 `WizardExtension` 사이 요소는 `</TemplateContent>` 및 `</VSTemplate>` 태그입니다. 대체는 *토큰* 의 값은 `PublicKeyToken` 이전 절차에서 가져온 공개 키 토큰을 사용 하 여 특성입니다.  
  
    ```xml  
    <WizardExtension>  
      <Assembly>ProjectTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=your token</Assembly>  
      <FullClassName>ProjectTemplateWizard.SiteColumnProjectWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     에 대 한 자세한 내용은 `WizardExtension` 요소 참조 [WizardExtension 요소 &#40;Visual Studio 템플릿&#41;](/visualstudio/extensibility/wizardextension-element-visual-studio-templates)합니다.  
  
3.  파일을 저장한 후 닫습니다.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-project-template"></a>프로젝트 템플릿에 있는 Elements.xml 파일에 대체 가능 매개 변수를 추가합니다.  
 Elements.xml 파일 SiteColumnProjectTemplate 프로젝트에 여러 개의 대체 가능 매개 변수를 추가 합니다. 이러한 매개 변수에서 초기화 되는 `RunStarted` 에서 메서드는 `SiteColumnProjectWizard` 앞에서 정의한 클래스입니다. 사용자가 사이트 열 프로젝트를 만들 때 Visual Studio는 자동으로 새 프로젝트에서 Elements.xml 파일에서 이러한 매개 변수를 마법사에서 지정한 값으로 바꿉니다.  
  
 대체 가능 매개 변수는 시작 하 고 달러 기호 ($) 문자로 끝나는 토큰입니다. 사용자 고유의 대체 가능 매개 변수를 정의 하는 것 외에도 정의 되어 있고 SharePoint 프로젝트 시스템에 의해 초기화 되는 기본 제공 매개 변수를 사용할 수 있습니다. 자세한 내용은 참조 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)합니다.  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Elements.xml 파일에 대체 가능 매개 변수를 추가 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Elements.xml 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
             Name="$fieldname$"   
             DisplayName="$fieldname$"   
             Type="$selectedfieldtype$"   
             Group="$selectedgrouptype$">  
      </Field>  
    </Elements>  
    ```  
  
     값을 변경 하는 새 XML는 `Name`, `DisplayName`, `Type`, 및 `Group` 특성을 사용자 지정 대체 가능 매개 변수입니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>VSIX 패키지를 마법사 추가  
 마법사는 사이트 열 프로젝트 템플릿이 포함 하는 VSIX 패키지를 배포 하려면 VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 마법사 프로젝트와 SharePoint 명령 프로젝트에 대 한 참조를 추가 합니다.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>마법사는 VSIX 패키지를 추가 하려면  
  
1.  **솔루션 탐색기**에 **SiteColumnProjectItem** 프로젝트에 대 한 바로 가기 메뉴를 열고는 **source.extension.vsixmanifest** 파일을 선택한 후 **열려**합니다.  
  
     Visual Studio 매니페스트 편집기에서 파일을 엽니다.  
  
2.  에 **자산** 탭 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.Assembly**합니다.  
  
4.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
5.  에 **프로젝트** 목록에서 선택 **ProjectTemplateWizard**를 선택한 후는 **확인** 단추입니다.  
  
6.  에 **자산** 탭 편집기의 선택은 **새로** 단추를 다시 합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
7.  에 **형식** 목록에서 입력 **SharePoint.Commands.v4**합니다.  
  
8.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
9. 에 **프로젝트** 목록에서 선택 된 **SharePointCommands** 프로젝트를 선택한 후는 **확인** 단추입니다.  
  
10. 메뉴 모음에서 **빌드**, **솔루션 빌드**, 솔루션이 오류 없이 빌드되는지 확인 합니다.  
  
## <a name="testing-the-wizard"></a>마법사를 테스트합니다.  
 이제 마법사를 테스트할 준비가 되었습니다. 먼저 Visual Studio의 실험적 인스턴스에서 SiteColumnProjectItem 솔루션 디버깅을 시작 합니다. 그런 다음 Visual Studio의 실험적 인스턴스에서 사이트 열 프로젝트에 대 한 마법사를 테스트 합니다. 마지막으로, 빌드 및 사이트 열이 예상 대로 작동 하는지 확인 하기 위해 프로젝트를 실행 합니다.  
  
#### <a name="to-start-debugging-the-solution"></a>솔루션 디버깅을 시작 하려면  
  
1.  관리 자격 증명으로 Visual Studio를 다시 시작 하 고 SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  ProjectTemplateWizard 프로젝트에서 SiteColumnProjectWizard 코드 파일을 열고 다음 코드의 첫 번째 줄에 중단점을 추가 `RunStarted` 메서드.  
  
3.  메뉴 모음에서 **디버그**, **예외**합니다.  
  
4.  에 **예외** 대화 상자에서 다음 사항을 확인는 **throw 됨** 및 **사용자가 처리** 에 대 한 확인란 **공용 언어 런타임 예외**이 삭제 되 고 선택 합니다는 **확인** 단추입니다.  
  
5.  선택 하 여 디버깅을 시작는 **F5** 키 또는 메뉴 모음 선택에서 **디버그**, **디버깅 시작**합니다.  
  
     Visual Studio에서는 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Site Column\1.0에 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>Visual Studio에서 마법사를 테스트 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **파일**, **새로**, **프로젝트**합니다.  
  
2.  확장은 **Visual C#** 노드 또는 **Visual Basic** 노드 (언어에 따라 프로젝트 템플릿은 지원)를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
3.  프로젝트 템플릿 목록에서 선택 **사이트 열**, 프로젝트 이름을 **SiteColumnWizardTest**를 선택한 후는 **확인** 단추입니다.  
  
4.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `RunStarted` 메서드.  
  
5.  프로젝트를 선택 하 여 디버깅을 계속는 **F5** 키 또는 메뉴 모음 선택에서 **디버그**, **계속**합니다.  
  
6.  에 **SharePoint 사용자 지정 마법사**, 디버깅을 위해 사용 하려는 사이트의 URL을 입력 한 다음 선택에서 **다음** 단추입니다.  
  
7.  두 번째 페이지에는 **SharePoint 사용자 지정 마법사**, 다음을 선택 합니다.  
  
    -   에 **형식** 목록에서 선택 **부울**합니다.  
  
    -   에 **그룹** 목록에서 선택 **사용자 지정 예/아니요 열**합니다.  
  
    -   에 **이름** 상자에 입력 **내 예/아니요 열**, 선택한 후는 **마침** 단추입니다.  
  
     **솔루션 탐색기**, 새 프로젝트에 표시 되 고 명명 된 프로젝트 항목이 포함 **Field1**, Visual Studio 편집기에서 프로젝트의 Elements.xml 파일을 엽니다.  
  
8.  Elements.xml 마법사에서 지정한 값이 들어 있는지 확인 합니다.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>Sharepoint에서 사이트 열을 테스트 하려면  
  
1.  Visual Studio의 실험적 인스턴스에서 F5 키를 선택 합니다.  
  
     사이트 열은 패키지 하 고 SharePoint에 배포 된 사이트는 **사이트 URL** 프로젝트의 속성을 지정 합니다. 이 사이트의 기본 페이지에는 웹 브라우저를 엽니다.  
  
    > [!NOTE]  
    >  경우는 **스크립트 디버깅 사용 안 함** 선택 대화 상자가 나타나면는 **예** 프로젝트 디버깅을 계속 하려면는 단추입니다.  
  
2.  에 **사이트 작업** 메뉴 선택 **사이트 설정**합니다.  
  
3.  사이트 설정 페이지에서 아래 **갤러리**, 선택는 **열 사이트** 링크 합니다.  
  
4.  사이트 열 목록에 있는지를 확인 한 **사용자 지정 예/아니요 열** 그룹 이라는 열이 포함 되어 **내 예/아니요 열**, 웹 브라우저를 닫습니다.  
  
## <a name="cleaning-up-the-development-computer"></a>개발 컴퓨터를 정리합니다.  
 프로젝트 항목의 테스트를 마친 후 프로젝트 템플릿을 Visual Studio의 실험적 인스턴스에서 제거 합니다.  
  
#### <a name="to-clean-up-the-development-computer"></a>개발 컴퓨터를 정리 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택 **사이트 열**를 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택은 **예** 단추에서 확장을 제거 하 고 다음을 선택 하도록 확인할 수는 **지금 다시 시작** 단추 제거를 완료 합니다.  
  
4.  Visual Studio의 실험적 인스턴스에서 CustomActionProjectItem 솔루션 열기의 인스턴스를 모두 닫습니다.  
  
     배포 하는 방법에 대 한 내용은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장 참조 [Visual Studio 확장명 전달](/visualstudio/extensibility/shipping-visual-studio-extensions)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 1 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio 템플릿 스키마 참조](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [방법: 프로젝트 템플릿에 마법사 사용](../extensibility/how-to-use-wizards-with-project-templates.md)  
  
  