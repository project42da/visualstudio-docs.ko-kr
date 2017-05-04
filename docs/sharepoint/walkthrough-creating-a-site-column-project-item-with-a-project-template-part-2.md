---
title: "연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 항목[Visual Studio에서 SharePoint 개발], 템플릿 만들기 마법사"
  - "SharePoint 프로젝트 항목, 템플릿 만들기 마법사"
  - "Visual Studio에서 Sharepoint 개발, 새 프로젝트 항목 형식 정의"
ms.assetid: da14207d-ac09-41ba-b387-c7f881b2a366
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부
  Visual Studio에서 SharePoint 프로젝트 항목의 사용자 지정 형식을 정의하여 프로젝트 템플릿과 연결한 후에는 템플릿에 대한 마법사를 제공할 수 있습니다.  마법사를 사용하면 사용자가 템플릿을 사용하여 해당 프로젝트 항목이 포함된 새 프로젝트를 만들 때 사용자에게서 정보를 수집할 수 있습니다.  수집한 정보는 프로젝트 항목을 초기화하는 데 사용될 수 있습니다.  
  
 이 연습에서는 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)에서 설명한 사이트 열 프로젝트 템플릿에 마법사를 추가합니다.  사용자가 사이트 열 프로젝트를 만들 때 마법사에서는 사이트 열에 대한 정보\(예: 기본 형식 및 그룹\)를 수집하고 이 정보를 새 프로젝트의 Elements.xml 파일에 추가합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트 템플릿과 연결된 사용자 지정 SharePoint 프로젝트 항목 형식을 위한 마법사 만들기  
  
-   Visual Studio에서 SharePoint 프로젝트를 위한 기본 제공 마법사와 유사한 사용자 지정 마법사 UI 정의.  
  
-   마법사가 실행되는 동안 로컬 SharePoint 사이트를 호출하는 데 사용되는 두 가지 *SharePoint 명령* 만들기.  SharePoint 명령은 Visual Studio 확장이 SharePoint 서버 개체 모델에서 API를 호출하기 위해 사용할 수 있는 메서드입니다.  자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
-   대체 가능한 매개 변수를 사용하여 마법사에서 수집한 데이터로 SharePoint 프로젝트 파일 초기화  
  
-   각각의 새 사이트 열 프로젝트 인스턴스에서 .snk 파일 새로 만들기  이 파일은 SharePoint 솔루션 어셈블리가 전역 어셈블리 캐시에 배포될 수 있도록 프로젝트 출력에 서명하는 데 사용됩니다.  
  
-   마법사 디버깅 및 테스트  
  
> [!NOTE]  
>  [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=191369](http://go.microsoft.com/fwlink/?LinkId=191369)에서 이 연습에 대한 완료된 프로젝트, 코드 및 기타 파일이 포함된 샘플을 다운로드할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 먼저 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)를 완료하여 SiteColumnProjectItem 솔루션을 만들어야 합니다.  
  
 또한 개발 컴퓨터에 다음 구성 요소가 있어야 이 연습을 완료할 수 있습니다.  
  
-   Windows, SharePoint 및 Visual Studio의 지원되는 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   The Visual Studio SDK.  이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   Visual Studio의 프로젝트 마법사 및 항목 템플릿 마법사.  자세한 내용은 [방법: 프로젝트 템플릿에 마법사 사용](../Topic/How%20to:%20Use%20Wizards%20with%20Project%20Templates.md) 및 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 참조하십시오.  
  
-   SharePoint의 사이트 열.  자세한 내용은 [Columns](http://go.microsoft.com/fwlink/?LinkId=183547)를 참조하십시오.  
  
##  <a name="wizardcomponents"></a> 마법사 구성 요소 이해  
 이 연습에서 보여 주는 마법사에는 몇 가지 구성 요소가 포함되어 있습니다.  다음 표에서는 이러한 구성 요소에 대해 설명합니다.  
  
|구성 요소|설명|  
|-----------|--------|  
|마법사 구현|<xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 `SiteColumnProjectWizard`라는 클래스입니다.  이 인터페이스는 마법사가 시작되고 완료될 때와 마법사 실행 중의 특정한 때에 Visual Studio에서 호출하는 메서드를 정의합니다.|  
|마법사 UI|`WizardWindow`라는 WPF 기반 창입니다.  이 창에는 `Page1` 및 `Page2`라는 두 가지 사용자 정의 컨트롤이 포함되어 있습니다.  이러한 사용자 정의 컨트롤은 마법사의 두 페이지를 나타냅니다.<br /><br /> 이 연습에서 마법사 구현의 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 메서드는 마법사 UI를 표시합니다.|  
|마법사 데이터 모델|마법사 UI와 마법사 구현 간의 계층을 제공하는 `SiteColumnWizardModel`이라는 중간 클래스입니다.  이 샘플에서는 이 클래스를 사용하여 마법사 구현과 마법사 UI를 서로 추상화합니다. 이 클래스는 모든 마법사의 필수 구성 요소가 아닙니다.<br /><br /> 이 연습에서 마법사 구현은 마법사 UI를 표시할 때 `SiteColumnWizardModel` 개체를 마법사 창에 전달합니다.  마법사 UI는 이 개체의 메서드를 사용하여 UI의 컨트롤 값을 저장하고 입력 사이트 URL이 유효한지 확인하는 등의 작업을 수행합니다.  사용자가 마법사를 완료한 후 마법사 구현은 `SiteColumnWizardModel` 개체를 사용하여 UI의 최종 상태를 확인합니다.|  
|프로젝트 서명 관리자|마법사 구현이 각각의 새 프로젝트 인스턴스에서 key.snk 파일을 새로 만드는 데 사용하는 `ProjectSigningManager`라는 도우미 클래스입니다.|  
|SharePoint 명령|마법사가 실행되는 동안 마법사 데이터 모델에서 로컬 SharePoint 사이트를 호출하는 데 사용하는 메서드입니다.  SharePoint 명령이 .NET Framework 3.5를 대상으로 해야 하기 때문에 이러한 명령은 마법사 코드의 나머지 부분과 다른 어셈블리에서 구현됩니다.|  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)에서 만든 SiteColumnProjectItem 솔루션에 몇 가지 프로젝트를 추가해야 합니다.  
  
-   WPF 프로젝트.  이 프로젝트에서 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하고 마법사 UI를 정의합니다.  
  
-   SharePoint 명령을 정의하는 클래스 라이브러리 프로젝트.  이 프로젝트는 .NET Framework 3.5를 대상으로 해야 합니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### WPF 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서, SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**에서, **SiteColumnProjectItem** 솔루션 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 프로젝트**를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 솔루션 노드가 표시됩니다.  
  
3.  **새 프로젝트 추가** 대화 상자 상단에 **.NET Framework 4.5** 가 .NET Framework 버전의 목록에서 선택되어 있는지 확인 합니다.  
  
4.  **Visual C\#** 노드 또는 **Visual Basic** 노드를 확장한 다음 **Windows** 노드를 선택합니다.  
  
5.  프로젝트 템플릿 목록에서, **WPF 사용자 컨트롤 라이브러리**을 선택하고, 프로젝트의 이름을 **ProjectTemplateWizard**로 설정한 **확인** 버튼을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 는 **ProjectTemplateWizard** 프로젝트를 솔루션에 추가하고 기본 UserControl1.xaml 코드 파일을 엽니다.  
  
6.  프로젝트에서 UserControl1.xaml 파일을 삭제합니다.  
  
#### SharePoint 명령 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서, SiteColumnProjectItem 솔루션 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음, **새 프로젝트**를 선택합니다.  
  
2.  **새 프로젝트 추가** 대화 상자의 상단에서, .NET Framework 버전 목록에서 **.NET Framework 3.5** 을 선택합니다.  
  
3.  **Visual C\#** 노드 또는  **Visual Basic** 노드를 확장한 다음 **Windows** 노드를 선택합니다.  
  
4.  **클래스 라이브러리** 프로젝트 템플릿을 선택하고, 프로젝트의 이름을 **SharePointCommands**로 설정한 다름, **확인** 버튼을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 는**SharePointCommands** 프로젝트를 솔루션에 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 프로젝트 구성  
 마법사를 만들기 전에 일부 코드 파일과 어셈블리 참조를 프로젝트에 추가해야 합니다.  
  
#### 마법사 프로젝트를 구성하려면  
  
1.  **솔루션 탐색기**에서, **프로젝트템플릿마법사** 프로젝트 노드의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **프로젝트 디자이너**에서, C\# 프로젝트에 대한 **응용 프로그램** 탭 혹은 Visual Basic 프로젝트용 **컴파일**을 선택합니다.  
  
3.  대상 프레임 워크가 .NET Framework 4.5 클라이언트 프로필이 아닌 .NET Framework 4.5로 설정되어 있는지 확인 하십시오.  
  
     자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md)을 참조하십시오.  
  
4.  **프로젝트템플릿마법사** 프로젝트에 대한 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
5.  **창 \(WPF\)** 항목을 선택하고, **WizardWindow**항목 이름을 짓고, **추가** 버튼을 선택합니다.  
  
6.  두 개의 **사용자 정의 컨트롤 \(WPF\)** 항목을 프로젝트에 추가하고, 그것들을 **페이지1** 및 **페이지2**로 이름 짓습니다.  
  
7.  프로젝트에 4개의 코드 파일을 추가하고, 그들에게 다음의 이름을 줍니다:  
  
    -   SiteColumnProjectWizard  
  
    -   SiteColumnWizardModel  
  
    -   ProjectSigningManager  
  
    -   CommandIds  
  
8.  **프로젝트템플릿마법사** 프로젝트 노드의 바로 가기 메뉴를 연 다음, **참조 추가**를 선택합니다.  
  
9. **어셈블리**노드를 확장하고, **확장** 노드와 다음 어셈블리의 확인란을 선택 합니다:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
10. 선택은 **확인** 버튼을 프로젝트에 어셈블리를 추가 하기 위해 선택합니다.  
  
11. **솔루션 탐색기**에서, **프로젝트템플릿마법사** 프로젝트의 **참조** 폴더 아래서, **EnvDTE**.를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **참조** 폴더가 표시됩니다.  
  
12. **속성** 창에서, **Interop 형식 포함** 속성을 **False** 값으로 변경합니다.  
  
13. Visual Basic 프로젝트를 개발하는 중이면, **프로젝트 디자이너**를 사용하여 ProjectTemplateWizard 네임스페이스를 프로젝트로 가져옵니다.  
  
     자세한 내용은 [방법: 가져온 네임스페이스 추가 또는 제거&#40;Visual Basic&#41;](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20(Visual%20Basic).md)을 참조하십시오.  
  
#### SharePointCommands 프로젝트를 구성하려면  
  
1.  **솔루션 탐색기**에서 **SharePointCommands** 프로젝트 노드를 선택합니다.  
  
2.  메뉴 모음에서, **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **기존 항목 추가** 대화 상자에서,프로젝트템플릿마법사 프로젝트의 코드 파일이 포함된 폴더로 이동하고, **명령Id** 코드 파일을 선택합니다.  
  
4.  **추가** 버튼 옆에 있는 화살표를 선택하고, 나타나는 메뉴의 **링크로 추가** 옵션을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 는 **SharePointCommands** 프로젝트에 링크로 코드 파일을 추가합니다.  코드 파일은 **프로젝트템플릿마법사** 프로젝트에 있지만, 파일의 코드는 **SharePointCommands** 프로젝트에도 컴파일됩니다.  
  
5.  **SharePointCommands** 프로젝트에서, Commands라는 다른 코드 파일을 추가합니다.  
  
6.  SharePointCommands 프로젝트를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
7.  **어셈블리**노드를 확장하고, **확장** 노드와 다음 어셈블리의 확인란을 선택 합니다:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
8.  **확인** 버튼을 프로젝트에 어셈블리를 추가 하기 위해 선택합니다.  
  
## 마법사 모델, 서명 관리자 및 SharePoint 명령 ID 만들기  
 샘플에서 다음 구성 요소를 구현하는 코드를 ProjectTemplateWizard 프로젝트에 추가합니다.  
  
-   SharePoint 명령 ID.  마법사에서 사용하는 SharePoint 명령을 식별하는 문자열입니다.  이 연습의 뒷부분에서 이러한 명령을 구현하는 코드를 SharePointCommands 프로젝트에 추가합니다.  
  
-   마법사 데이터 모델  
  
-   프로젝트 서명 관리자  
  
 이러한 구성 요소에 대한 자세한 내용은 [마법사 구성 요소 이해](#wizardcomponents)를 참조하십시오.  
  
#### SharePoint 명령 ID를 정의하려면  
  
1.  ProjectTemplateWizard 프로젝트에서 CommandIds 코드 파일을 열고이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#5](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/commandids.cs#5)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#5](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/commandids.vb#5)]  
  
#### 마법사 모델을 만들려면  
  
1.  SiteColumnWizardModel 코드 파일을 열고이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/sitecolumnwizardmodel.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/sitecolumnwizardmodel.vb#6)]  
  
#### 프로젝트 서명 관리자를 만들려면  
  
1.  ProjectSigningManager 코드 파일을 열고이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#8](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/projectsigningmanager.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#8](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/projectsigningmanager.vb#8)]  
  
## 마법사 UI 만들기  
 마법사 창의 UI 및 마법사 페이지에 UI를 제공하는 두 가지 사용자 정의 컨트롤을 정의하는 XAML을 추가하고 창과 사용자 정의 컨트롤의 동작을 정의하는 코드를 추가합니다.  만드는 마법사는 Visual Studio의 SharePoint 프로젝트에 대한 기본 제공 마법사와 유사합니다.  
  
> [!NOTE]  
>  다음 단계에서는 XAML 또는 코드를 프로젝트에 추가한 후 프로젝트에서 컴파일 오류가 발생합니다.  이러한 오류는 이후 단계에서 코드를 추가하면 사라집니다.  
  
#### 마법사 창 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트에서, WizardWindow.xaml 파일에 대한 바로 가기 메뉴를 열고 선택한 후 디자이너에서 창을 열기 위해 **열기** 을 선택합니다.  
  
2.  디자이너의 XAML 뷰에서 현재 XAML을 다음 XAML로 바꿉니다.  이 XAML에서는 제목, 마법사 페이지가 포함된 <xref:System.Windows.Controls.Grid> 및 창 아래쪽의 탐색 단추가 포함된 UI를 정의합니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#10](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/wizardwindow.xaml#10)]  
  
    > [!NOTE]  
    >  이 XAML에서 만들어지는 창은 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> 기본 클래스에서 파생됩니다.  사용자 지정 WPF 대화 상자를 Visual Studio에 추가하는 경우 다른 Visual Studio 대화 상자와 일관성 있는 스타일을 사용하고 발생할 수 있는 모달 대화 상자 문제를 방지하기 위해 이 클래스에서 대화 상자를 파생시키는 것이 좋습니다.  자세한 내용은 [만들기 및 관리 모달 대화 상자](../extensibility/creating-and-managing-modal-dialog-boxes.md)을 참조하십시오.  
  
3.  Visual Basic 프로젝트를 개발하는 중이면, `Window` 요소의 `x:Class` 특성에 있는 `WizardWindow` 클래스 이름에서 `ProjectTemplateWizard` 네임스페이스를 제거합니다.  이 요소는 XAML의 첫 번째 줄에 있습니다.  지금까지 작업을 마친 후, 첫 번째 줄은 다음과 같습니다.  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml 파일의 코드 숨김 파일을 엽니다.  
  
5.  다음 코드를 사용하여 파일의 맨 위에 있는 `using` 선언을 제외한, 파일의 내용을 대체합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#4](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/wizardwindow.xaml.cs#4)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#4](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/wizardwindow.xaml.vb#4)]  
  
#### 첫 번째 마법사 페이지 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트에서, Page1.xaml 파일에 대한 바로 가기 메뉴를 열고 선택한 후 디자이너에서 사용자 컨트롤을 열기 위해 **열기** 을 선택합니다.  
  
2.  디자이너의 XAML 뷰에서 현재 XAML을 다음 XAML로 바꿉니다.  XAML에서는 사용자가 디버깅에 사용할 로컬 사이트의 URL을 입력할 수 있는 텍스트 상자에 포함 된 UI를 정의 합니다.  UI는 사용자가 프로젝트에 샌드박스가 적용 되는지 여부를 지정할 수 있습니다 옵션 단추가 포함 됩니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#11](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/page1.xaml#11)]  
  
3.  Visual Basic 프로젝트를 개발하는 중이면 `UserControl` 요소의 `x:Class` 특성에 있는 `Page1` 클래스 이름에서 `ProjectTemplateWizard` 네임스페이스를 제거합니다.  이 네임스페이스는 XAML의 첫 번째 줄에 있습니다.  지금까지 작업을 마친 후의 첫 번째 줄은 다음과 같습니다.  
  
    ```  
    <UserControl x:Class="Page1"  
    ```  
  
4.  다음 코드를 사용하여 파일의 맨 위에 있는 `using` 선언을 제외한, Page1.xaml 파일의 내용을 대체합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/page1.xaml.cs#2)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/page1.xaml.vb#2)]  
  
#### 두 번째 마법사 페이지 UI를 만들려면  
  
1.  ProjectTemplateWizard 프로젝트의 Page2.xaml 파일에 대 한 바로 가기 메뉴를 열고 **열기**를 선택합니다.  
  
     사용자 정의 컨트롤이 디자이너에서 열립니다.  
  
2.  XAML 뷰에서, 현재 XAML를 다음 XAML로 바꿉니다.  이 XAML에서는 사이트 열의 기본 형식을 선택하기 위한 드롭다운 목록, 갤러리에 사이트 열을 표시할 기본 제공 그룹 또는 사용자 지정 그룹을 지정하기 위한 콤보 상자 및 사이트 열의 이름을 지정하기 위한 텍스트 상자가 포함된 UI를 정의합니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#12](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/page2.xaml#12)]  
  
3.  Visual Basic 프로젝트를 개발하는 중이면 `UserControl` 요소의 `x:Class` 특성에 있는 `Page2` 클래스 이름에서 `ProjectTemplateWizard` 네임스페이스를 제거합니다.  이 네임스페이스는 XAML의 첫 번째 줄에 있습니다.  지금까지 작업을 마친 후의 첫 번째 줄은 다음과 같습니다.  
  
    ```  
    <UserControl x:Class="Page2"  
    ```  
  
4.  다음 코드를 사용하여 파일의 맨 위에 있는 `using` 선언을 제외하고 .Page2.xaml 파일에 대한 코드 숨김 파일의 내용을 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#3](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/page2.xaml.cs#3)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/page2.xaml.vb#3)]  
  
## 마법사 구현  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하여 마법사의 기본 기능을 정의합니다.  이 인터페이스는 마법사가 시작되고 완료될 때와 마법사 실행 중의 특정한 때에 Visual Studio에서 호출하는 메서드를 정의합니다.  
  
#### 마법사를 구현하려면  
  
1.  ProjectTemplateWizard 프로젝트에서 SiteColumnProjectWizard 코드 파일을 엽니다.  
  
2.  이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#7](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projecttemplatewizard/sitecolumnprojectwizard.cs#7)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#7](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projecttemplatewizard/sitecolumnprojectwizard.vb#7)]  
  
## SharePoint 명령 만들기  
 SharePoint 서버 개체 모델을 호출하는 두 개의 사용자 지정 명령을 만듭니다.  한 명령은 사용자가 마법사에서 입력하는 사이트 URL이 유효한지 여부를 확인합니다.  다른 명령은 사용자가 새 사이트 열의 기반으로 사용할 필드 형식을 선택할 수 있도록 지정된 SharePoint 사이트에서 모든 필드 형식을 가져옵니다.  
  
#### SharePoint 명령을 정의하려면  
  
1.  **SharePointCommands** 프로젝트에서 Commands 코드 파일을 엽니다.  
  
2.  이 파일의 전체 내용을 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#9](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/sharepointcommands/commands.cs#9)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#9](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/sharepointcommands/commands.vb#9)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 마법사를 위한 모든 코드가 프로젝트에 포함되었습니다.  프로젝트를 빌드하여 오류 없이 컴파일되는지 확인합니다.  
  
#### 프로젝트를 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## 프로젝트 템플릿에서 key.snk 파일 제거  
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)에서 만든 프로젝트 템플릿에는 각 사이트 열 프로젝트 인스턴스에 서명하는 데 사용되는 key.snk 파일이 포함되어 있습니다.  이제 마법사에서 각 프로젝트에 대한 새 key.snk 파일을 생성하기 때문에 이 key.snk 파일은 더 이상 필요하지 않습니다.  프로젝트 템플릿에서 key.snk 파일을 제거하고 이 파일에 대한 참조를 제거합니다.  
  
#### 프로젝트 템플릿에서 key.snk 파일을 제거하려면  
  
1.  **솔루션 탐색기**에서, **SiteColumnProjectTemplate** 노드 아래서, **key.snk** 파일에 대한 바로 가기 메뉴를 연 후 **삭제**를 선택합니다.  
  
2.  확인 대화 상자가 나타나면 **예** 단추를 선택합니다.  
  
3.  **SiteColumnProjectTemplate** 노드 아래에서, SiteColumnProjectTemplate.vstemplate 파일을 연 후 여기에서 다음 요소를 제거 합니다.  
  
    ```  
    <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
    ```  
  
4.  파일을 저장한 후 닫습니다.  
  
5.  **SiteColumnProjectTemplate** 노드 아래에서, ProjectTemplate.csproj 또는 ProjectTemplate.vbproj 파일을 열고 다음 `PropertyGroup` 요소를 제거합니다.  
  
    ```  
    <PropertyGroup>  
      <SignAssembly>true</SignAssembly>  
      <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
    </PropertyGroup>  
    ```  
  
6.  다음 `None` 요소를 제거합니다.  
  
    ```  
    <None Include="key.snk" />  
    ```  
  
7.  파일을 저장한 후 닫습니다.  
  
## 마법사를 프로젝트 템플릿과 연결  
 마법사를 구현했으므로 이 마법사를 **사이트 열** 프로젝트 템플릿과 연결해야 합니다.  이렇게 하려면 세 가지 절차를 완료해야 합니다.  
  
1.  강력한 이름으로 마법사 어셈블리에 서명합니다.  
  
2.  마법사 어셈블리의 공개 키 토큰을 가져옵니다.  
  
3.  **사이트 열** 프로젝트 템플릿의 .vstemplate 파일에서 마법사 어셈블리에 대한 참조를 추가합니다.  
  
#### 강력한 이름으로 마법사 어셈블리에 서명하려면  
  
1.  **솔루션 탐색기**에서, **ProjectTemplateWizard** 프로젝트의 바로 가기 메뉴를 연 후 **속성**을 선택합니다.  
  
2.  **서명** 탭에서 **어셈블리 서명** 확인란을 선택합니다.  
  
3.  **강력한 이름 키 파일 선택** 목록에서 **\<새로 만들기...\>**를 선택합니다.  
  
4.  **강력한 이름 키 만들기** 대화 상자에서, 새 키 파일의 이름을 입력하고, **암호로 내 키 파일 보호** 확인란의 선택을 취소하고 **확인**버튼을 선택합니다.  
  
5.  **ProjectTemplateWizard** 프로젝트의 바로 가기 메뉴를 선택한 다음 **빌드** 를 선택하여 ProjectTemplateWizard.dll 파일을 만들 수 있습니다.  
  
#### 마법사 어셈블리의 공개 키 토큰을 가져오려면  
  
1.  **시작 메뉴** 에서, **모든 프로그램**을 선택하고, **Microsoft Visual Studio** 을 선택하고, **Visual Studio Tools**를 선택한 다음 **개발자 명령 프롬프트**를 선택합니다.  
  
     Visual Studio 명령 프롬프트 창을 엽니다.  
  
2.  *PathToWizardAssembly* 를 개발 컴퓨터에서 ProjectTemplateWizard 프로젝트를 위해 빌드된 ProjectTemplateWizard.dll 어셈블리의 전체 경로로 바꾸어 다음 명령을 실행합니다.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     ProjectTemplateWizard.dll 어셈블리의 공개 키 토큰은 Visual Studio 명령 프롬프트 창에 기록됩니다.  
  
3.  Visual Studio 명령 프롬프트 창을 계속 열어 둡니다.  공개 키 토큰은 다음 절차 중에 필요합니다.  
  
#### 마법사 어셈블리에 대한 참조를 .vstemplate 파일에 추가하려면  
  
1.  **솔루션 탐색기**에서 **SiteColumnProjectTemplate** 프로젝트 노드를 확장하고 SiteColumnProjectTemplate.vstemplate 파일을 엽니다.  
  
2.  파일의 끝 부분에서 `</TemplateContent>` 및 `</VSTemplate>` 태그 사이에 다음 `WizardExtension` 요소를 추가합니다.  이전 절차에서 가져온 공개 키의 `PublicKeyToken` 속성의 *your token* 값으로 바꿉니다.  
  
    ```  
    <WizardExtension>  
      <Assembly>ProjectTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=your token</Assembly>  
      <FullClassName>ProjectTemplateWizard.SiteColumnProjectWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     `WizardExtension` 요소에 대한 자세한 내용은 [WizardExtension 요소&#40;Visual Studio 템플릿&#41;](../extensibility/wizardextension-element-visual-studio-templates.md)를 참조하십시오.  
  
3.  파일을 저장한 후 닫습니다.  
  
## 프로젝트 템플릿의 Elements.xml 파일에 대체 가능한 매개 변수 추가  
 대체 가능한 매개 변수 여러 개를 SiteColumnProjectTemplate 프로젝트의 Elements.xml 파일에 추가합니다.  이러한 매개 변수는 앞에서 정의한 `SiteColumnProjectWizard` 클래스의 `RunStarted` 메서드에서 초기화됩니다.  사용자가 사이트 열 프로젝트를 만들면 Visual Studio에서는 자동으로 새 프로젝트의 Elements.xml 파일에 있는 이러한 매개 변수를 마법사에서 지정한 값으로 바꿉니다.  
  
 대체 가능한 매개 변수는 달러 기호\($\) 문자로 시작하고 끝나는 토큰입니다.  대체 가능한 매개 변수를 직접 정의할 뿐 아니라 SharePoint 프로젝트 시스템에 의해 정의되고 초기화되는 기본 제공 매개 변수를 사용할 수도 있습니다.  자세한 내용은 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)을 참조하십시오.  
  
#### 대체 가능한 매개 변수를 Elements.xml 파일에 추가하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Elements.xml 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
             Name="$fieldname$"   
             DisplayName="$fieldname$"   
             Type="$selectedfieldtype$"   
             Group="$selectedgrouptype$">  
      </Field>  
    </Elements>  
    ```  
  
     새로운 XML에서는 `Name`, `DisplayName`, `Type` 및 `Group` 특성의 값을 대체 가능한 사용자 지정 매개 변수로 변경합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## VSIX 패키지에 마법사 추가  
 사이트 열 프로젝트 템플릿이 포함된 VSIX 패키지를 사용하여 마법사를 배포하려면 마법사 프로젝트와 SharePoint 명령 프로젝트에 대한 참조를 VSIX 프로젝트의 source.extension.vsixmanifest 파일에 추가합니다.  
  
#### VSIX 패키지에 마법사를 추가하려면  
  
1.  **솔루션 탐색기**에서, **SiteColumnProjectItem** 프로젝트에서, **source.extension.vsixmanifest** 파일에 대한 바로 가기 메뉴를 열고 **열기**를 선택합니다.  
  
     매니페스트 편집기에서 파일이 열립니다.  
  
2.  편집기의 **자산** 탭에서 **New** 버튼을 선택합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  **유형** 목록에서, **Microsoft.VisualStudio.Assembly**를 선택합니다.  
  
4.  **원본** 목록에서, **현재 솔루션의 프로젝트**를 선택합니다.  
  
5.  **프로젝트** 목록에서, **ProjectTemplateWizard**를 선택한 다음, **확인** 단추를 선택합니다.  
  
6.  편집기의 **자산** 탭에서, **New** 버튼을 다시 선택합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
7.  **유형** 목록에서, **SharePoint.Commands.v4**을 입력합니다.  
  
8.  **원본** 목록에서, **현재 솔루션의 프로젝트**를 선택합니다.  
  
9. **프로젝트** 목록에서, **SharePointCommands** 프로젝트를 선택한 다음 **확인** 버튼을 선택합니다.  
  
10. 선택 메뉴 모음에서, **빌드**, **솔루션 빌드**를 선택하여 솔루션이 오류없이 빌드되는지 확인합니다.  
  
## 마법사 테스트  
 이제 마법사를 테스트할 준비가 되었습니다.  우선 실험 모드의 Visual Studio 인스턴스에서 SiteColumnProjectItem 솔루션 디버깅을 시작합니다.  그런 다음 실험 모드의 Visual Studio 인스턴스에서 사이트 열 프로젝트에 대한 마법사를 테스트합니다.  마지막으로, 프로젝트를 빌드 및 실행하여 사이트 열이 예상대로 작동하는지 확인합니다.  
  
#### 솔루션 디버깅을 시작하려면  
  
1.  관리자 권한으로 Visual Studio를 다시 시작한 다음 SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  ProjectTemplateWizard 프로젝트에서 SiteColumnProjectWizard 코드 파일을 열고 `RunStarted` 메서드의 코드 첫 줄에 중단점을 추가합니다.  
  
3.  메뉴 모음에서 **디버그**, **예외**를 선택합니다.  
  
4.  **예외** 대화 상자에서 **Common Language Runtime Exceptions**에 대해 **Throw됨** 및 **사용자가 처리하지 않음** 확인란의 선택이 취소되어 있는지 확인하고, **확인**버튼을 선택합니다.  
  
5.  **F5** 키를 선택 또는, 메뉴 모음에서 **디버깅**, **디버깅 시작**을 선택하여 디버깅을 시작합니다.  
  
     Visual Studio에서는 확장을 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0Exp\\Extensions\\Contoso\\Site Column\\1.0에 설치하고 실험 모드의 Visual Studio 인스턴스를 시작합니다.  이 Visual Studio 인스턴스에서 프로젝트 항목을 테스트합니다.  
  
#### Visual Studio에서 마법사를 테스트하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 메뉴 바의 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  프로젝트 템플릿에서 지원하는 언어에 따라 **Visual C\#** 노드 또는 **Visual Basic** 노드를 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  프로젝트 템플릿 목록에서 **사이트 열** 을 선택하고 프로젝트를 **SiteColumnWizardTest** 로 이름짓고, **확인** 버튼을 선택합니다.  
  
4.  다른 Visual Studio 인스턴스의 코드가 이전에 `RunStarted` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  
  
5.  **F5** 키를 선택하거나 메뉴 모음에서 **디버그**, **계속**을 선택하여 프로젝트 디버그를 계속합니다.  
  
6.  **SharePoint 사용자 지정 마법사**에서 디버깅에 사용할 사이트의 URL을 입력하고 **다음**을 클릭합니다.  
  
7.  **SharePoint 사용자 지정 마법사**의 두 번째 페이지에서 다음과 같이 선택합니다.  
  
    -   **유형** 목록에서 **부울**를 선택한다.  
  
    -   **그룹** 목록에서, **사용자 지정 예\/아니요 열**을 선택합니다.  
  
    -   **이름** 상자에서, 내 예\/아니요 열을 입력 한 다음 **완료** 버튼을 선택합니다.  
  
     새 프로젝트가 **Field1**이라는 프로젝트 항목과 함께 **솔루션 탐색기**에 나타나고 Visual Studio는 프로젝트의 Elements.xml 파일이 편집기에서 열리게 합니다.  
  
8.  마법사에서 지정한 값이 Elements.xml에 포함되어 있는지 확인합니다.  
  
#### SharePoint에서 사이트 열을 테스트하려면  
  
1.  Visual Studio의 실험적 인스턴스에서, F5 키를 선택합니다.  
  
     사이트 열은 패키지되고 프로젝트가 지정한 **사이트 URL** 속성의 SharePoint 사이트로 배포됩니다.  이 사이트의 기본 페이지가 웹 브라우저에서 열립니다.  
  
    > [!NOTE]  
    >  **스크립트 디버깅 사용 안 함** 대화 상자가 표시되면 **예** 단추를 선택하여 프로젝트를 계속 디버깅합니다.  
  
2.  **사이트 동작** 메뉴에서 **사이트 설정**을 선택합니다.  
  
3.  사이트 설정 페이지에서 **갤러리** 아래에서, **사이트 열** 링크를 선택합니다.  
  
4.  사이트 열의 목록에서, **내 예\/아니요 열** 이라는 열이 포함된 **사용자 지정 예\/아니요 열** 그룹이 있는지 확인하고 웹 브라우저를 닫습니다.  
  
## 개발 컴퓨터 정리  
 프로젝트 항목의 테스트를 마쳤으면 실험 모드의 Visual Studio 인스턴스에서 프로젝트 템플릿을 제거합니다.  
  
#### 개발 컴퓨터를 정리하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 메뉴 모음에서 **도구**, **확장 및 업데이트**를 선택합니다.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장 목록에서 **사이트 열** 확장자를 선택한 다음 **제거** 버튼을 선택합니다.  
  
3.  대화 상자가 나타나면, **예** 버튼을 선택하여 확장명을 제거한 다음 **지금 다시 시작** 버튼을 선택하여 제거를 완료 합니다.  
  
4.  Visual Studio의 두 인스턴스, 즉 실험 모드의 인스턴스와 CustomActionProjectItem 솔루션이 열려 있는 Visual Studio 인스턴스를 모두 닫습니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장 배포에 대한 자세한 내용은 다음을 참조하십시오. [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md).  
  
## 참고 항목  
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [방법: 프로젝트 템플릿에 마법사 사용](../Topic/How%20to:%20Use%20Wizards%20with%20Project%20Templates.md)  
  
  