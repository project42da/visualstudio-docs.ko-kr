---
title: "Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2"
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
  - "project items [SharePoint development in Visual Studio], creating template wizards"
  - "SharePoint project items, creating template wizards"
  - "SharePoint development in Visual Studio, defining new project item types"
ms.assetid: 2d8165d3-4af9-4a5e-bdba-8b2a06b1dc8d
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2
  Visual Studio에서 SharePoint 프로젝트 항목의 사용자 지정 형식을 정의하여 항목 템플릿과 연결한 후에는 템플릿에 대한 마법사를 제공할 수 있습니다.  마법사를 사용하면 사용자가 템플릿을 사용하여 해당 프로젝트 항목의 새 인스턴스를 프로젝트에 추가할 때 사용자에게서 정보를 수집할 수 있습니다.  수집한 정보는 프로젝트 항목을 초기화하는 데 사용될 수 있습니다.  
  
 이 연습에서는 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)에서 설명한 사용자 지정 작업 프로젝트 항목에 마법사를 추가합니다.  사용자가 사용자 지정 작업 프로젝트 항목을 SharePoint 프로젝트에 추가 하는 경우 마법사가 사용자 지정 작업 \(예: 위치 및 최종 사용자가 선택할 때 탐색할 URL\)에 대 한 정보를 수집 하 고이 정보를 새 프로젝트 항목에서의 Elements.xml 파일에 추가 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   항목 템플릿과 연결된 사용자 지정 SharePoint 프로젝트 항목 형식을 위한 마법사 만들기  
  
-   Visual Studio에서 SharePoint 프로젝트 항목을 위한 기본 제공 마법사와 유사한 사용자 지정 마법사 UI 정의.  
  
-   대체 가능한 매개 변수를 사용하여 마법사에서 수집한 데이터로 SharePoint 프로젝트 파일 초기화  
  
-   마법사 디버깅 및 테스트  
  
> [!NOTE]  
>  완료 된 프로젝트, 코드 및 기타 파일을 다음 위치에서이 연습에 포함 되어 있는 예제를 다운로드할 수 있습니다: [SharePoint 도구 확장 연습에 대 한 프로젝트 파일](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## 사전 요구 사항  
 이 연습을 수행하려면 먼저 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)를 완료하여 CustomActionProjectItem 솔루션을 만들어야 합니다.  
  
 또한 개발 컴퓨터에 다음 구성 요소가 있어야 이 연습을 완료할 수 있습니다.  
  
-   지원 되는 버전의 Windows, SharePoint 및 Visual Studio.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio SDK입니다.  이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   Visual Studio의 프로젝트 마법사 및 항목 템플릿 마법사.  자세한 내용은 [방법: 프로젝트 템플릿에 마법사 사용](~/extensibility/how-to-use-wizards-with-project-templates.md) 및 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 참조하십시오.  
  
-   SharePoint의 사용자 지정 작업.  자세한 내용은 [Custom Action](http://go.microsoft.com/fwlink/?LinkId=177800)을 참조하십시오.  
  
## 마법사 프로젝트 만들기  
 이 연습을 완료 하려면 프로젝트에서 만든 CustomActionProjectItem 솔루션에 추가 해야 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  이 프로젝트에서 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하고 마법사 UI를 정의합니다.  
  
#### 마법사 프로젝트를 만들려면  
  
1.  Visual Studio CustomActionProjectItem 솔루션을 엽니다  
  
2.  **솔루션 탐색기**, 솔루션 노드 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
3.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 또는  **Visual Basic** 노드를 다음 선택은  **Windows** 노드.  
  
4.  상단에 있는  **새 프로젝트** 대화 상자에서 있는지 확인 하십시오  **.NET Framework 4.5** .NET Framework 버전의 목록에서 선택 됩니다.  
  
5.  선택은  **WPF 사용자 컨트롤 라이브러리** : 프로젝트 이름, 프로젝트 템플릿  **ItemTemplateWizard**, 다음 선택은  **확인** 단추.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 **ItemTemplateWizard** 프로젝트를 솔루션에 추가합니다.  
  
6.  프로젝트에서 UserControl1 항목을 삭제합니다.  
  
## 마법사 프로젝트 구성  
 마법사를 만들기 전에 Windows Presentation Foundation \(WPF\) 창, 코드 파일 및 어셈블리 참조를 프로젝트에 추가 해야 합니다.  
  
#### 마법사 프로젝트를 구성하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴에서 열을  **ItemTemplateWizard** 프로젝트 노드 및 다음 선택  **속성**.  
  
2.  에 있는  **프로젝트 디자이너**,.NET Framework 4.5로 대상 프레임 워크 설정 되어 있는지 확인 하십시오.  
  
     C\# 프로젝트의 경우이 값을 설정할 수 있는  **응용 프로그램** 탭입니다.  Visual Basic 프로젝트의 경우이 값을 설정할 수 있는  **컴파일** 탭.  자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](~/ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하십시오.  
  
3.  에  **ItemTemplateWizard** 프로젝트에 추가 된  **창 \(WPF\)** 프로젝트에 항목을 만든 후 다음 항목의 이름을  **WizardWindow**.  
  
4.  문자열 및 CustomActionWizard 라는 두 개의 코드 파일을 추가 합니다.  
  
5.  바로 가기 메뉴를 열고를  **ItemTemplateWizard** 프로젝트를 하 고 선택  **참조 추가**.  
  
6.  에  **참조 관리자\-ItemTemplateWizard** 대화 상자에서  **어셈블리** 노드를 선택 된  **확장** 노드.  
  
7.  다음 어셈블리 옆에 있는 확인란을 선택 하 고 선택 된  **확인** 단추:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
8.  **솔루션 탐색기**에  **참조** ItemTemplateWizard 프로젝트에 대 한 폴더를 선택은  **EnvDTE** 참조.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **참조** 폴더가 표시됩니다.  
  
9. 에  **속성** 창에서 값을 변경의  **Interop 형식 포함** 속성을  **False**.  
  
## 사용자 지정 작업의 기본 위치 및 ID 문자열 정의  
 모든 사용자 지정 작업에는 Elements.xml 파일에 있는 `CustomAction` 요소의 `GroupID` 및 `Location` 특성으로 지정되는 위치 및 ID가 있습니다.  이 단계에서는 ItemTemplateWizard 프로젝트에서 이러한 특성에 지정할 수 있는 올바른 문자열을 정의합니다.  이 연습을 완료 하면 사용자의 위치 및 ID를 마법사에서 지정 하는 경우 사용자 지정 작업 프로젝트 항목의 Elements.xml 파일에 이러한 문자열이 기록 됩니다.  
  
 이 샘플에서는 복잡성을 줄이기 위해 사용 가능한 기본 위치 및 ID의 하위 집합만 지원합니다.  전체 목록은 [Default Custom Action Locations and IDs](http://go.microsoft.com/fwlink/?LinkId=181964)를 참조하십시오.  
  
#### 기본 위치 및 ID 문자열을 정의하려면  
  
1.  엽니다.  
  
2.  에 있는  **ItemTemplateWizard** 프로젝트에 문자열 코드 파일의 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/strings.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/strings.vb#6)]  
  
## 마법사 UI 만들기  
 마법사의 UI를 정의하기 위해 XAML을 추가하고 마법사의 일부 컨트롤을 ID 문자열에 바인딩하기 위해 일부 코드를 추가합니다.  만드는 마법사는 Visual Studio의 SharePoint 프로젝트에 대한 기본 제공 마법사와 유사합니다.  
  
#### 마법사 UI를 만들려면  
  
1.  에  **ItemTemplateWizard** 프로젝트에 대 한 바로 가기 메뉴를 엽니다의  **WizardWindow.xaml** 파일을 및 다음 선택  **열기** 창 디자이너에서 엽니다.  
  
2.  XAML 뷰에서 현재 XAML을 다음 XAML로 바꿉니다.  이 XAML에서는 제목, 사용자 지정 작업의 동작을 지정하기 위한 컨트롤 및 창 아래쪽의 탐색 단추가 포함된 UI를 정의합니다.  
  
    > [!NOTE]  
    >  이 코드를 추가한 후 프로젝트에 컴파일 오류가 발생 해야 합니다.  이러한 오류는 이후 단계에서 코드를 추가하면 사라집니다.  
  
     [!code-xml[SPExtensibility.ProjectItem.CustomAction#9](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/wizardwindow.xaml#9)]  
  
    > [!NOTE]  
    >  이 XAML에서 생성 되는 창에서 파생 되는 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> 기본 클래스입니다.  사용자 지정 WPF 대화 상자 Visual Studio 추가 하면 대화 상자를 다른 대화 상자에 Visual Studio 일관성 있는 스타일 및 모달 대화 상자가 발생할 수 있는 문제를 방지 하려면이 클래스에서 파생 하는 것이 좋습니다.  자세한 내용은 [만들기 및 관리 모달 대화 상자](../extensibility/creating-and-managing-modal-dialog-boxes.md)을 참조하십시오.  
  
3.  Visual Basic 프로젝트를 개발 하는 경우 제거는 `ItemTemplateWizard` 네임 스페이스에서의 `WizardWindow` 클래스 이름에는 `x:Class` 특성은 `Window` 요소.  이 요소에는 XAML의 첫 번째 줄에 있습니다.  완료 되 면 첫 번째 줄에 다음 코드를 유사 합니다.  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml 파일에 대 한 코드 숨김 파일에 현재 코드를 다음 코드로 대체 합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#7](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/wizardwindow.xaml.cs#7)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#7](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/wizardwindow.xaml.vb#7)]  
  
## 마법사 구현  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하여 마법사의 기능을 정의합니다.  
  
#### 마법사를 구현하려면  
  
1.  에 있는  **ItemTemplateWizard** 열린 프로젝트의  **CustomActionWizard** 파일에서 코드 및 다음이 파일에 현재 코드를 다음 코드로 바꿉니다:  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#8](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/customactionwizard.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#8](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/customactionwizard.vb#8)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 마법사를 위한 모든 코드가 프로젝트에 포함되었습니다.  프로젝트를 빌드하여 오류 없이 컴파일되는지 확인합니다.  
  
#### 프로젝트를 빌드하려면  
  
1.  메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**.  
  
## 마법사를 항목 템플릿과 연결  
 마법사를 구현 했으므로를 함께 연결 해야 여  **사용자 지정 작업** 세 가지 주요 단계를 수행 하 여 항목 템플릿:  
  
1.  강력한 이름으로 마법사 어셈블리에 서명합니다.  
  
2.  마법사 어셈블리의 공개 키 토큰을 가져옵니다.  
  
3.  **사용자 지정 작업** 항목 템플릿의 .vstemplate 파일에서 마법사 어셈블리에 대한 참조를 추가합니다.  
  
#### 강력한 이름으로 마법사 어셈블리에 서명하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴에서 열을  **ItemTemplateWizard** 프로젝트 노드 및 다음 선택  **속성**.  
  
2.  **서명** 탭에서 **어셈블리 서명** 확인란을 선택합니다.  
  
3.  에 있는  **강력한 이름 키 파일 선택** 목록에서 선택  **\< 새로... \>**.  
  
4.  에  **강력한 이름 키 만들기** 대화 상자에서 선택을 취소의 이름을 입력은  **암호로 내 키 파일 보호** 확인란을 선택한 다음 선택은  **확인** 단추.  
  
5.  메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**.  
  
#### 마법사 어셈블리의 공개 키 토큰을 가져오려면  
  
1.  Visual Studio 명령 프롬프트 창에서 다음을 실행 명령 대체  *PathToWizardAssembly* 빌드된 ItemTemplateWizard.dll 어셈블리의 ItemTemplateWizard 프로젝트 개발 컴퓨터에 전체 경로를입니다.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     ItemTemplateWizard.dll 어셈블리의 공개 키 토큰은 Visual Studio 명령 프롬프트 창에 기록됩니다.  
  
2.  Visual Studio 명령 프롬프트 창을 계속 열어 둡니다.  다음 절차를 완료 하려면 공개 키 토큰이 필요 합니다.  
  
#### 마법사 어셈블리에 대한 참조를 .vstemplate 파일에 추가하려면  
  
1.  **솔루션 탐색기**, 확장 된  **ItemTemplate** 프로젝트 노드 및 ItemTemplate.vstemplate 파일을 엽니다.  
  
2.  파일의 끝 부분에서 `</TemplateContent>` 및 `</VSTemplate>` 태그 사이에 다음 `WizardExtension` 요소를 추가합니다.  교체는  *YourToken* 의 값은 `PublicKeyToken` 특성은 이전 절차에서 얻은 공개 키 토큰으로.  
  
    ```  
    <WizardExtension>  
      <Assembly>ItemTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=YourToken</Assembly>  
      <FullClassName>ItemTemplateWizard.CustomActionWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     `WizardExtension` 요소에 대한 자세한 내용은 [WizardExtension 요소&#40;Visual Studio 템플릿&#41;](../extensibility/wizardextension-element-visual-studio-templates.md)를 참조하십시오.  
  
3.  파일을 저장한 후 닫습니다.  
  
## 항목 템플릿의 Elements.xml 파일에 대체 가능한 매개 변수 추가  
 대체 가능한 매개 변수 여러 개를 ItemTemplate 프로젝트의 Elements.xml 파일에 추가합니다.  이러한 매개 변수는 앞에서 정의한 `CustomActionWizard` 클래스의 `PopulateReplacementDictionary` 메서드에서 초기화됩니다.  사용자가 프로젝트에 사용자 지정 작업 프로젝트 항목을 추가하면 Visual Studio에서는 자동으로 새 프로젝트 항목의 Elements.xml 파일에 있는 이러한 매개 변수를 마법사에서 지정한 값으로 바꿉니다.  
  
 대체 가능한 매개 변수는 달러 기호 \($\) 문자로 시작 하는 토큰입니다.  대체 가능한 매개 변수를 정의할 뿐 아니라 SharePoint 프로젝트 시스템을 정의 하 고 초기화 하는 기본 제공 매개 변수를 사용할 수 있습니다.  자세한 내용은 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)을 참조하십시오.  
  
#### 대체 가능한 매개 변수를 Elements.xml 파일에 추가하려면  
  
1.  ItemTemplate 프로젝트의 Elements.xml 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="$IdValue$"  
                    GroupId="$GroupIdValue$"  
                    Location="$LocationValue$"  
                    Sequence="1000"  
                    Title="$TitleValue$"  
                    Description="$DescriptionValue$" >  
        <UrlAction Url="$UrlValue$"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     새로운 XML은 `Id`, `GroupId`, `Location`, `Description` 및 `Url` 특성의 값을 대체 가능한 매개 변수로 변경합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## VSIX 패키지에 마법사 추가  
 VSIX 프로젝트에서에서 source.extension.vsixmanifest 파일을 프로젝트 항목이 포함 된 VSIX 패키지와 함께 배포 되도록 마법사 프로젝트에 대 한 참조를 추가 합니다.  
  
#### VSIX 패키지에 마법사를 추가하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴에서 열을  **source.extension.vsixmanifest** CustomActionProjectItem 프로젝트에서 파일 및 다음 선택  **열기** 매니페스트 편집기에서 파일을 열려고.  
  
2.  매니페스트 편집기에서 선택 된  **자산** 탭을 클릭 한 다음 선택은  **새로** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
3.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.Assembly**.  
  
4.  에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
5.  에  **프로젝트** 목록에서 선택  **ItemTemplateWizard**, 다음 선택은  **확인** 단추입니다.  
  
6.  메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**, 및 다음 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
## 마법사 테스트  
 이제 마법사를 테스트할 준비가 되었습니다.  첫째, Visual Studio 실험적 인스턴스에서 CustomActionProjectItem 솔루션 디버깅을 시작 합니다.  다음 마법사 사용자 지정 작업 프로젝트 항목에 대 한 Visual Studio 실험적 인스턴스에 SharePoint 프로젝트에서 테스트 합니다.  마지막으로, SharePoint 프로젝트를 빌드 및 실행하여 사용자 지정 작업이 예상대로 작동하는지 확인합니다.  
  
#### 솔루션 디버깅을 시작 하려면  
  
1.  Visual Studio 관리자 자격 증명으로 다시 시작 하 고 CustomActionProjectItem 솔루션을 엽니다.  
  
2.  ItemTemplateWizard 프로젝트에 CustomActionWizard 코드 파일을 열고 다음 코드의 첫째 줄에 중단점을 추가 된 `RunStarted` 메서드입니다.  
  
3.  메뉴 표시줄에서 선택  **디버깅**,  **예외**.  
  
4.  에  **예외** 대화 상자에서 있는지 확인 하십시오의  **throw 됨** 및  **사용자가 처리 하지 않음** 확인란을  **공용 언어 런타임 예외** 선택을 하 고 선택의  **확인** 단추.  
  
5.  선택, F5 키를 선택 하거나, 메뉴 모음에서 디버깅 시작  **디버깅**,  **디버깅 시작**.  
  
     Visual Studio 작업 프로젝트 Item\\1.0 %userprofile%\\appdata\\local\\microsoft\\visualstudio\\11.0exp\\extensions\\contoso\\custom에 있는 확장을 설치 및 Visual Studio 실험 인스턴스를 시작 합니다.  프로젝트 항목에 Visual Studio이 인스턴스를 테스트 합니다.  
  
#### Visual Studio에서 마법사를 테스트하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **파일**,  **New**,  **프로젝트**.  
  
2.  확장은  **C\#** 또는  **Visual Basic** 노드 \(항목 템플릿을 지 원하는 언어에 따라\)의  **SharePoint** 노드를 다음 선택은  **2010** 노드.  
  
3.  프로젝트 템플릿 목록에서 선택  **SharePoint 2010 프로젝트**, 프로젝트의 이름을  **CustomActionWizardTest**, 다음 선택은  **확인** 단추입니다.  
  
4.  에  **SharePoint 사용자 지정 마법사**디버깅에 사용 하려는 사이트의 URL을 입력 하 고 다음 선택의  **마침** 단추.  
  
5.  **솔루션 탐색기**, 프로젝트 노드에 대 한 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 항목**.  
  
6.  에  **새 항목 추가\-CustomItemWizardTest** 대화 상자에서 확장은  **SharePoint** 노드를 차례로 확장 하 고는  **2010** 노드.  
  
7.  프로젝트 항목의 목록에서 선택의  **사용자 지정 작업** 항목을 및 다음 선택은  **추가** 단추.  
  
8.  다른 Visual Studio 인스턴스의 코드가 이전에 `RunStarted` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  
  
9. 계속 하려면 F5 키를 선택 하 여 또는 메뉴 표시줄에서 선택 하 여 프로젝트를 디버깅  **디버깅**,  **계속**.  
  
     SharePoint 사용자 지정 마법사가 나타납니다.  
  
10. 아래  **위치**, 선택은  **목록 편집** 옵션 단추.  
  
11. 에 있는  **그룹 ID** 목록에서 선택  **통신**.  
  
12. 에 있는  **제목** 상자에 입력  **SharePoint 개발자 센터**.  
  
13. 에 있는  **설명이** 상자에 입력  **SharePoint 개발자 센터 웹 사이트를 엽니다**.  
  
14. 에  **URL** 상자에 입력  **http:\/\/msdn.microsoft.com\/sharepoint\/default.aspx**, 다음 선택은  **마침** 단추입니다.  
  
     isual Studio 라는 항목 추가  **CustomAction1** 프로젝트와의 Elements.xml 파일을 편집기에서 엽니다.  마법사에서 지정한 값이 Elements.xml에 포함되어 있는지 확인합니다.  
  
#### SharePoint에서 사용자 지정 작업을 테스트하려면  
  
1.  실험적 인스턴스를 Visual Studio f 5 키를 선택 하거나 메뉴 표시줄에서 선택  **디버깅**,  **디버깅 시작**.  
  
     사용자 지정 작업을 패키지 하 고 지정 된 SharePoint 사이트에 배포 된  **사이트 URL** 속성에서 프로젝트 및 웹 브라우저를이 사이트의 기본 페이지에 열립니다.  
  
    > [!NOTE]  
    >  경우는  **스크립트 디버깅 사용 안 함** 대화 상자가 나타나며, 선택의  **예** 단추.  
  
2.  SharePoint 사이트의 목록 영역에서 선택 된  **작업** 링크입니다.  
  
     **작업\-모든 작업** 페이지가 나타납니다.  
  
3.  에  **목록 도구** 탭 리본 메뉴의 선택은  **목록** 탭을 한 다음의  **설정** 을  그룹, 선택  **목록 설정**.  
  
     **목록 설정** 페이지가 나타납니다.  
  
4.  아래는  **통신** 페이지의 위쪽에 제목, 선택은  **SharePoint 개발자 센터** 연결 브라우저 웹 사이트 http:\/\/msdn.microsoft.com\/sharepoint\/default.aspx에서 열린다는 것을 확인 하 고 다음 브라우저를 닫습니다.  
  
## 개발 컴퓨터 정리  
 프로젝트 항목의 테스트를 마쳤으면 실험 모드의 Visual Studio 인스턴스에서 프로젝트 항목 템플릿을 제거합니다.  
  
#### 개발 컴퓨터를 정리하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **도구**,  **확장 및 업데이트**.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장명 목록에서 선택의  **사용자 지정 작업 프로젝트 항목** 확장명을 다음 선택은  **제거** 단추.  
  
3.  나타나는 대화 상자에서 선택 된  **예** 확장명을 제거 하 고 선택 확인 단추는  **지금 다시 시작** 단추 제거를 완료 합니다.  
  
4.  Visual Studio \(Visual Studio CustomActionProjectItem 솔루션에 열려 있는 인스턴스 및 실험적 인스턴스\)을 모두 닫습니다.  
  
## 참고 항목  
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [방법: 프로젝트 템플릿에 마법사 사용](~/extensibility/how-to-use-wizards-with-project-templates.md)   
 [Default Custom Action Locations and IDs](http://go.microsoft.com/fwlink/?LinkId=181964)  
  
  