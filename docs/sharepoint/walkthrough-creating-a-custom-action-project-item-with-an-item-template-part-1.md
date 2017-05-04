---
title: "Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint project items, creating custom templates"
  - "SharePoint project items, defining your own types"
  - "project items [SharePoint development in Visual Studio], defining your own types"
  - "SharePoint development in Visual Studio, defining new project item types"
ms.assetid: 41ed9c1c-4239-4d80-934b-975fde744288
caps.latest.revision: 152
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 151
---
# Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1
  고유한 프로젝트 항목 형식을 만들어 Visual Studio에서 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  이 연습에서는 SharePoint 사이트에 사용자 지정 작업을 만들기 위해 SharePoint 프로젝트에 추가할 수 있는 프로젝트 항목을 만듭니다.  사용자 지정 작업은 SharePoint 사이트의 **사이트 작업** 메뉴에 메뉴 항목을 추가합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용자 지정 작업에 대한 새로운 형식의 SharePoint 프로젝트 항목을 정의하는 Visual Studio 확장 만들기.  새 프로젝트 항목 형식은 몇 가지 사용자 지정 기능을 구현합니다.  
  
    -   Visual Studio에서 사용자 지정 작업용 디자이너 표시 등 프로젝트 항목과 관련된 추가 작업을 위한 시작점으로 사용되는 바로 가기 메뉴  
  
    -   개발자가 프로젝트 항목 및 프로젝트 항목을 포함하는 프로젝트의 특정 속성을 변경할 때 실행되는 코드  
  
    -   **솔루션 탐색기**에서 프로젝트 항목 옆에 표시되는 사용자 지정 아이콘  
  
-   프로젝트 항목에 대한 Visual Studio 항목 템플릿 만들기  
  
-   프로젝트 항목 템플릿과 확장 어셈블리를 배포하기 위한 VSIX\(Visual Studio Extension\) 패키지 빌드  
  
-   프로젝트 항목 디버깅 및 테스트  
  
 이 연습은 독립적으로 실행할 수 있습니다.  이 연습을 완료한 후에는 항목 템플릿에 마법사를 추가하여 프로젝트 항목을 개선할 수 있습니다.  자세한 내용은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)을 참조하십시오.  
  
> [!NOTE]  
>  [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=191369](http://go.microsoft.com/fwlink/?LinkId=191369)에서 이 연습에 대한 완료된 프로젝트, 코드 및 기타 파일이 포함된 샘플을 다운로드할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows, SharePoint 및 Visual Studio 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   SharePoint의 사용자 지정 작업.  사용자 지정 작업에 대한 자세한 내용은  [Custom Action](http://go.microsoft.com/fwlink/?LinkId=177800)을 참조하십시오.  
  
-   Visual Studio의 항목 템플릿.  자세한 내용은 [Visual Studio에서 사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)을 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 세 프로젝트를 만들어야 합니다.  
  
-   VSIX 프로젝트.  이 프로젝트는 SharePoint 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  
  
-   항목 템플릿 프로젝트.  이 프로젝트는 SharePoint 프로젝트에 SharePoint 프로젝트 항목을 추가하는 데 사용할 수 있는 항목 템플릿을 만듭니다.  
  
-   클래스 라이브러리 프로젝트.  이 프로젝트는 SharePoint 프로젝트 항목의 동작을 정의하는 Visual Studio 확장을 구현합니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  **새 프로젝트** 대화 상자 맨 위의 콤보 상자에서 **.NET Framework 4.5**가 선택되어 있는지 확인합니다.  
  
4.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 노드를 확장한 다음 **확장성** 노드를 선택합니다.  
  
    > [!NOTE]  
    >  **확장성** 노드는 Visual Studio 2010 SDK를 설치한 경우에만 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
5.  **VSIX 프로젝트** 템플릿을 선택합니다.  
  
6.  **이름** 텍스트 상자에 **CustomActionProjectItem**를 입력하고 **확인** 단추를 누릅니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **CustomActionProjectItem** 프로젝트를 추가합니다.  
  
#### 항목 템플릿 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **솔루션** 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 새 프로젝트를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  **새 프로젝트** 대화 상자 맨 위의 콤보 상자에서 **.NET Framework 4.5**가 선택되어 있는지 확인합니다.  
  
3.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 노드를 확장한 다음 **확장성** 노드를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 **C\# 항목 템플릿** 또는 **Visual Basic 항목 템플릿**을 선택합니다.  
  
5.  **이름** 텍스트 상자에서 **ItemTemplate**를 입력한 후 **확인** 단추를 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 **ItemTemplate** 프로젝트를 솔루션에 추가합니다.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **솔루션** 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 새 프로젝트를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자 맨 위의 콤보 상자에서 **.NET Framework 4.5**가 선택되어 있는지 확인합니다.  
  
3.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 노드 중 하나를 확장하고 **Windows** 노드를 선택하고 나서 **클래스 라이브러리** 템플릿을 선택합니다.  
  
4.  **이름** 텍스트 상자에 **ProjectItemDefinition**을 입력한 후 **확인** 단추를 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **ProjectItemDefinition** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 확장 프로젝트 구성  
 SharePoint 프로젝트 항목 형식을 정의하는 코드를 작성하기 전에 코드 파일과 어셈블리 참조를 확장 프로젝트에 추가해야 합니다.  
  
#### 프로젝트를 구성하려면  
  
1.  **솔루션 탐색기**에서 **ProjectItemDefinition** 프로젝트의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
2.  프로젝트 항목 목록에서 **아이콘 파일**을 클릭합니다.  
  
3.  **이름** 텍스트 상자에 **CustomAction** 이름과 적절한 파일 이름 확장명을 입력하고, **추가**를 선택합니다.  
  
4.  **솔루션 탐색기**에서 프로젝트의  **ProjectItemDefinition** 프로젝트에 대한 바로 가기 메뉴를 열고 **참조 추가**를 선택합니다.  
  
5.  **참조 관리자 \- ProjectItemDefinition** 대화 상자에서 **어셈블리** 노드를 선택한 다음 **프레임 워크** 노드를 선택합니다.  
  
6.  다음 각 어셈블리 옆의 확인란을 선택합니다.  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
7.  **확장** 노드를 선택하고, Microsoft.VisualStudio.Sharepoint 어셈블리 옆에 있는 확인란을 선택한 다음  **확인** 단추를 선택합니다.  
  
## 새 SharePoint 프로젝트 항목 형식 정의  
 새 프로젝트 항목 형식의 동작을 정의하기 위해 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  새 프로젝트 항목 형식을 정의하려는 경우 항상 이 인터페이스를 구현합니다.  
  
#### 새 SharePoint 프로젝트 항목 형식을 정의하려면  
  
1.  ProjectItemDefinition 프로젝트에서 CustomAction 코드 파일을 엽니다.  
  
2.  이 파일의 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/projectitemtypedefinition/customaction.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/projectitemdefinition/customaction.vb#1)]  
  
## 솔루션 탐색기에서 프로젝트 항목의 아이콘 만들기  
 사용자 지정 SharePoint 프로젝트 항목을 만들 때 이미지\(아이콘 또는 비트맵\)를 프로젝트 항목에 연결할 수 있습니다.  이 이미지는 **솔루션 탐색기**에서 프로젝트 항목 옆에 표시됩니다.  
  
 다음 절차에서는 프로젝트 항목의 아이콘을 만들고 확장 어셈블리에 이 아이콘을 포함합니다.  이 아이콘은 앞서 만든 `CustomActionProjectItemTypeProvider` 클래스의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute>를 통해 참조됩니다.  
  
#### 프로젝트 항목의 사용자 지정 아이콘을 만들려면  
  
1.  **솔루션 탐색기**에서 **ProjectItemDefinition** 프로젝트의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
2.  프로젝트 항목의 목록에서 **아이콘 파일**을 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서 **아이콘 파일** 항목을 보려면 **일반** 노드를 클릭해야 합니다.  
  
3.  **이름** 텍스트 상자에**CustomAction\_SolutionExplorer.ico**를 입력한 다음 **추가** 단추를 선택합니다.  
  
     새 아이콘이 **이미지 편집기**에서 열립니다.  
  
4.  디자인을 인식할 수 있도록 16x16 버전의 아이콘 파일을 편집한 다음 아이콘 파일을 저장합니다.  
  
5.  **솔루션 탐색기**에서 **CustomAction\_SolutionExplorer.ico**를 선택합니다.  
  
6.  **속성** 창에서 **빌드 작업** 속성의 옆에 있는 화살표를 선택합니다.  
  
7.  표시된 목록에서 **Embedded Resource**를 선택합니다.  
  
## 검사점  
 이 연습의 이전 단계를 통해 프로젝트 항목을 위한 모든 코드가 프로젝트에 포함되었습니다.  프로젝트를 빌드하여 오류 없이 컴파일되는지 확인합니다.  
  
#### 프로젝트를 빌드하려면  
  
1.  **ProjectItemDefinition** 프로젝트에 대한 바로 가기 메뉴를 열고 **빌드**를 선택합니다.  
  
## Visual Studio 항목 템플릿 만들기  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 하려면 프로젝트 템플릿이나 항목 템플릿을 만들어야 합니다.  개발자는 Visual Studio의 이러한 템플릿을 통해 새 프로젝트를 만들거나 기존 프로젝트에 항목을 추가하여 프로젝트 인스턴스를 만듭니다.  이 연습을 위해 ItemTemplate 프로젝트를 사용하여 프로젝트 항목을 구성합니다.  
  
#### 항목 템플릿을 만들려면  
  
1.  ItemTemplate 프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
2.  ItemTemplate 프로젝트에서 ItemTemplate.vstemplate 파일을 엽니다.  
  
3.  이 파일의 내용을 다음 XML로 바꾼 다음 파일을 저장하고 닫습니다.  
  
    > [!NOTE]  
    >  다음 XML은 Visual C\# 항목 템플릿에 사용됩니다.  Visual Basic 항목 템플릿을 만드는 중이라면 `ProjectType` 요소의 값을 `VisualBasic`으로 바꿉니다.  
  
    ```  
  
    <VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
      <TemplateData>  
        <DefaultName>CustomAction</DefaultName>  
        <Name>Custom Action</Name>  
        <Description>SharePoint Custom Action by Contoso</Description>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>1000</SortOrder>  
        <Icon>ItemTemplate.ico</Icon>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
      <TemplateContent>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\Elements.xml">Elements.xml</ProjectItem>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\SharePointProjectItem.spdata">CustomAction.spdata</ProjectItem>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     이 파일에서는 항목 템플릿의 내용과 동작을 정의합니다.  이 파일의 내용에 대한 자세한 내용은 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)를 참조하십시오.  
  
4.  **솔루션 탐색기**에서 **항목 템플릿** 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
5.  **새 항목 추가** 대화 상자에서 **텍스트 파일** 템플릿을 선택합니다.  
  
6.  **이름** 상자에 **CustomAction.spdata**를 입력한 다음 **추가** 단추를 선택합니다.  
  
7.  CustomAction.spdata 파일에 다음 XML을 추가한 다음 파일을 저장하고 닫습니다.  
  
    ```  
  
    <ProjectItem Type="Contoso.CustomAction" DefaultFile="Elements.xml"   
     xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$fileinputname$\" Type="ElementManifest" />  
      </Files>  
    </ProjectItem>  
    ```  
  
     이 파일에는 프로젝트 항목에 포함된 파일에 대한 정보가 들어 있습니다.  `ProjectItem` 요소의 `Type` 특성을 프로젝트 항목 정의\(이 연습의 앞부분에서 만든 `CustomActionProjectItemTypeProvider` 클래스\)의 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>에 전달되는 것과 동일한 문자열로 설정해야 합니다.  .spdata 파일의 내용에 대한 자세한 내용은 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)를 참조하십시오.  
  
8.  **솔루션 탐색기**에서 **항목 템플릿** 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
9. **새 항목 추가** 대화 상자에서 **XML 파일** 템플릿을 선택합니다.  
  
10. **이름** 상자에 **Elements.xml**을 입력한 다음 **추가** 단추를 선택합니다.  
  
11. Elements.xml 파일의 내용을 다음 XML로 바꾼 다음 파일을 저장하고 닫습니다.  
  
    ```  
  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="Replace this with a GUID or some other unique string"  
                    GroupId="SiteActions"  
                    Location="Microsoft.SharePoint.StandardMenu"  
                    Sequence="1000"  
                    Title="Replace this with your title"  
                    Description="Replace this with your description" >  
        <UrlAction Url="~site/Lists/Tasks/AllItems.aspx"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     이 파일에서는 SharePoint 사이트의 **사이트 작업** 메뉴에 메뉴 항목을 만드는 기본 사용자 지정 작업을 정의합니다.  사용자가 메뉴 항목을 선택하면 `UrlAction` 요소에 지정된 URL이 웹 브라우저에서 열립니다.  사용자 지정 작업을 정의하는 데 사용할 수 있는 XML 요소에 대한 자세한 내용은 [Custom Action Definitions](http://go.microsoft.com/fwlink/?LinkId=177801)를 참조하십시오.  
  
12. 필요한 경우 ItemTemplate.ico 파일을 열고 수정하여 아이콘을 쉽게 식별할 수 있게 디자인합니다.  이 아이콘은 **새 항목 추가** 대화 상자에서 프로젝트 항목 옆에 표시됩니다.  
  
13. **솔루션 탐색기**에서 **항목 템플릿** 프로젝트의 바로 가기 메뉴를 열고 **프로젝트 언로드**를 선택합니다.  
  
14. **항목 템플릿** 프로젝트의 바로 가기 메뉴를 연 다음에 **편집 ItemTemplate.csproj** 또는 **편집 ItemTemplate.vbproj**을 선택합니다.  
  
15. 프로젝트 파일에서 다음 `VSTemplate` 요소를 찾습니다.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
    ```  
  
16. 이 `VSTemplate` 요소를 다음 XML로 바꾼 다음 파일을 저장하고 닫습니다.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` 요소는 프로젝트를 빌드할 때 항목 템플릿이 만들어지는 경로에 폴더를 추가로 지정합니다.  이 곳에 지정된 폴더는 고객이 **새 항목 추가** 대화 상자를 열고 **SharePoint** 노드를 확장하고 나서 **2010** 노드를 선택해야지만 항목 템플릿이 사용 가능하다는 것을 확실하게 합니다.  
  
17. **솔루션 탐색기**에서 **항목 템플릿** 프로젝트의 바로 가기 메뉴를 열고 **프로젝트 다시 로드**를 선택합니다.  
  
## 프로젝트 항목을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  먼저 VSIX 프로젝트에 포함된 source.extension.vsixmanifest 파일을 수정하여 VSIX 패키지를 구성합니다.  그런 다음 솔루션을 빌드하여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하고 만들려면  
  
1.  **솔루션 탐색기**에서 CustomActionProjectItem 프로젝트의 **source.extension.vsixmanifest** 파일에 대한 바로 가기 메뉴를 연 후 **열기**를 선택합니다.  
  
     매니페스트 편집기에서 파일이 열립니다.  source.extension.vsixmanifest 파일은 모든 VSIX 패키지에 필요한 extension.vsixmanifest 파일의 기초를 제공합니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  **제품 이름** 상자에 **Custom Action Project Item**을 입력합니다.  
  
3.  **만든 이** 상자에 **Contoso**를 입력합니다.  
  
4.  **설명** 상자에 **사용자 지정 작업을 나타내는 SharePoint 프로젝트 항목**을 입력합니다.  
  
5.  **자산** 탭에서, **새로 만들기** 단추를 선택합니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
6.  **유형** 목록에서, **Microsoft.VisualStudio.ItemTemplate**를 선택합니다.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `ItemTemplate` 요소에 해당합니다.  이 요소는 프로젝트 항목 템플릿이 포함된 VSIX 패키지의 하위 폴더를 식별합니다.  자세한 내용은 [NIB: ItemTemplate Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/1d489e54-c1c5-4f96-a510-6c2640867ff0)을 참조하십시오.  
  
7.  **원본** 목록에서 **현재 솔루션의 프로젝트**를 선택합니다.  
  
8.  **프로젝트** 목록에서 **항목 템플릿**을 선택한 다음 **확인** 단추를 선택합니다.  
  
9. **자산** 탭에서, **새로 만들기** 단추를 다시 선택합니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
10. **유형** 목록에서, **Microsoft.VisualStudio.MefComponent**를 선택합니다.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
11. **원본** 목록에서 **현재 솔루션의 프로젝트**를 선택합니다.  
  
12. **프로젝트** 목록에서 **프로젝트 항목 정의**를 선택합니다.  
  
13. **확인** 단추를 선택합니다.  
  
14. 선택 메뉴 모음에서, **빌드**, **솔루션 빌드**를 선택하여 프로젝트가 오류없이 컴파일되는지 확인합니다.  
  
15. CustomActionProjectItem 프로젝트의 빌드 출력 폴더가 CustomActionProjectItem.vsix 파일을 포함하고 있는지 확인하십시오.  
  
     기본적으로, 빌드 출력 폴더는 CustomActionProjectItem 프로젝트가 있는 폴더 아래의 ..\\bin\\Debug 폴더입니다.  
  
## 프로젝트 항목 테스트  
 이제 프로젝트 항목을 테스트할 준비가 되었습니다.  우선 실험 모드의 Visual Studio 인스턴스에서 CustomActionProjectItem 솔루션 디버깅을 시작합니다.  그런 다음 실험 모드의 Visual Studio 인스턴스에서 SharePoint 프로젝트의 **사용자 지정 작업** 프로젝트 항목을 테스트합니다.  마지막으로, SharePoint 프로젝트를 빌드 및 실행하여 사용자 지정 작업이 예상대로 작동하는지 확인합니다.  
  
#### 솔루션 디버깅을 시작하려면  
  
1.  관리자 권한으로 Visual Studio를 다시 시작하고 CustomActionProjectItem 솔루션을 엽니다.  
  
2.  CustomAction 코드 파일을 열고 `InitializeType` 메서드의 코드 첫째 줄에 중단점을 추가합니다.  
  
3.  **F5** 키를 선택하여 디버깅을 시작합니다.  
  
     Visual Studio에서는 확장을 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\10.0Exp\\Extensions\\Contoso\\Custom Action Project Item\\1.0에 설치하고 실험 모드의 Visual Studio 인스턴스를 시작합니다.  이 Visual Studio 인스턴스에서 프로젝트 항목을 테스트합니다.  
  
#### Visual Studio에서 프로젝트 항목을 테스트하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 메뉴 바의 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  항목 템플릿에서 지원하는 언어에 따라 **Visual C\#** 또는 **Visual Basic**을 확장하고 **SharePoint**를 확장한 다음 **2010** 노드를 선택합니다.  
  
3.  프로젝트 템플릿 목록에서 **SharePoint 2010**을 선택합니다.  
  
4.  **이름** 상자에서 **CustomActionTest**를 입력한 후 **확인** 단추를 선택합니다.  
  
5.  **SharePoint 사용자 지정 마법사**에서 디버깅에 사용할 사이트의 URL을 입력하고 **마침**을 클릭합니다.  
  
6.  **솔루션 탐색기**에서 프로젝트 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
7.  **새 항목 추가** 대화 상자의 **SharePoint** 노드 아래에서 **2010** 노드를 선택합니다.  
  
     **사용자 지정 작업** 항목이 프로젝트 항목의 목록에 표시되는지 확인합니다.  
  
8.  **사용자 지정 작업** 항목을 선택한 다음, **추가** 단추를 선택합니다.  
  
     **CustomAction1**이라는 항목이 프로젝트에 추가되고 Elements.xml 파일이 편집기에서 열립니다.  
  
9. 다른 Visual Studio 인스턴스의 코드가 이전에 `InitializeType` 메서드에 설정한 중단점에서 중지하는지 확인합니다.  
  
10. 프로젝트 디버깅을 계속하려면 **F5** 단추를 선택합니다.  
  
11. 실험 모드의 Visual Studio 인스턴스의 **솔루션 탐색기**에서 **CustomAction1**의 바로 가기 메뉴를 연 다음, **사용자 지정 작업 디자이너 보기**를 선택합니다.  
  
12. 메시지 상자가 나타나는지 확인한 다음 **확인** 단추를 선택합니다.  
  
     이 바로 가기 메뉴를 사용하여 사용자 지정 작업용 디자이너 표시 등의 추가 옵션이나 명령을 개발자에게 제공할 수 있습니다.  
  
13. 메뉴 모음에서 **보기**, **출력**을 선택합니다.  
  
     **출력** 창이 열립니다.  
  
14. **솔루션 탐색기**에서 **CustomAction1** 항목에 대한 바로 가기 메뉴를 연 다음, **MyCustomAction**으로 이름을 변경합니다.  
  
     **출력** 창에 확인 메시지가 나타납니다.  이 메세지는  `CustomActionProjectItemTypeProvider` 에서 정의한 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemNameChanged> 이벤트 처리기에서 작성한 것입니다.  이 이벤트와 기타 프로젝트 항목 이벤트를 처리하여 개발자가 프로젝트 항목을 수정할 때의 사용자 지정 동작을 구현할 수 있습니다.  
  
#### SharePoint에서 사용자 지정 작업을 테스트하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 **MyCustomAction** 프로젝트 항목의 자식인 Elements.xml 파일을 엽니다.  
  
2.  Elements.xml 파일에 다음과 같이 변경하고 파일을 저장합니다.  
  
    -   `CustomAction`  요소에서,  `Id`  특성을 다음 예제와 같이 GUID 또는 고유의 문자열로 설정하십시오.  
  
        ```  
        Id="cd85f6a7-af2e-44ab-885a-0c795b52121a"  
        ```  
  
    -   `CustomAction` 요소에서, 다음 예제와 같이 `Title` 특성을 설정하십시오.  
  
        ```  
        Title="SharePoint Developer Center"  
        ```  
  
    -   `CustomAction` 요소에서, 다음 예제와 같이 `Description` 특성을 설정하십시오.  
  
        ```  
        Description="Opens the SharePoint Developer Center Web site."  
        ```  
  
    -   `UrlAction` 요소에서, 다음 예제와 같이 `Url` 특성을 설정하십시오.  
  
        ```  
        Url="http://msdn.microsoft.com/sharepoint/default.aspx"  
        ```  
  
3.  F5 키를 선택합니다.  
  
     사용자 지정 작업이 패키징되어 프로젝트의 **사이트 URL** 속성에 지정된 SharePoint 사이트로 배포됩니다.  이 사이트의 기본 페이지가 웹 브라우저에서 열립니다.  
  
    > [!NOTE]  
    >  **스크립트 디버깅 사용 안 함** 대화 상자가 표시되면 **예** 단추를 선택하여 프로젝트를 계속 디버깅합니다.  
  
4.  **사이트 작업** 메뉴에서 **SharePoint 개발자 센터**를 선택한 다음, 브라우저에서 http:\/\/msdn.microsoft.com\/sharepoint\/default.aspx 페이지가 열리는지 확인한 다음 웹 브라우저를 닫습니다.  
  
## 개발 컴퓨터 정리  
 프로젝트 항목의 테스트를 마쳤으면 실험 모드의 Visual Studio 인스턴스에서 프로젝트 항목 템플릿을 제거합니다.  
  
#### 개발 컴퓨터를 정리하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 **도구** 메뉴의 **확장 및 업데이트**를 선택합니다.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장 목록에서 **Custom Action Project Item**을 선택한 다음 **제거**를 클릭합니다.  
  
3.  나타나는 대화 상자에서 **예** 단추를 선택하여 확장을 제거합니다.  
  
4.  **지금 다시 시작** 단추를 선택하여 제거를 완료합니다.  
  
5.  Visual Studio의 두 인스턴스, 즉 실험 모드의 인스턴스와 CustomActionProjectItem 솔루션이 열려 있는 Visual Studio 인스턴스를 모두 닫습니다.  
  
## 다음 단계  
 이 연습을 완료한 후에는 항목 템플릿에 마법사를 추가할 수 있습니다.  사용자가 SharePoint 프로젝트에 사용자 지정 작업 프로젝트 항목을 추가하면 이 마법사는 사용자 지정 작업에 대한 정보\(예: 사용자 지정 작업 선택 시 이동할 위치 및 URL\)를 수집하고 이 정보를 새 프로젝트 항목의 Elements.xml 파일에 추가합니다.  자세한 내용은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)을 참조하십시오.  
  
## 참고 항목  
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [Image Editor for Icons](/visual-cpp/windows/image-editor-for-icons)   
 [Creating an Icon or Other Image &#40;Image Editor for Icons&#41;](/visual-cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  