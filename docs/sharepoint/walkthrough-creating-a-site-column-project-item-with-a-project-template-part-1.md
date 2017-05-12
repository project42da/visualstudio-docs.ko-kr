---
title: "연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부"
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
  - "SharePoint 프로젝트 항목, 고유 형식 정의"
  - "프로젝트 항목[Visual Studio에서 SharePoint 개발], 고유 형식 정의"
  - "SharePoint 프로젝트, 사용자 지정 템플릿 만들기"
  - "Visual Studio에서 Sharepoint 개발, 새 프로젝트 항목 형식 정의"
ms.assetid: b53d48d7-cbf2-45c2-9537-06a6819be397
caps.latest.revision: 60
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 59
---
# 연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부
  SharePoint 프로젝트는 하나 이상의 SharePoint 프로젝트 항목을 위한 컨테이너입니다.  사용자 고유의 SharePoint 프로젝트 항목 형식을 만든 다음 프로젝트 템플릿과 연결하여 Visual Studio에서 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  이 연습에서는 사이트 열을 만들기 위한 프로젝트 항목 형식을 정의한 다음 사이트 열 프로젝트 항목이 포함된 새 프로젝트를 만드는 데 사용할 수 있는 프로젝트 템플릿을 만듭니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사이트 열에 대한 새로운 형식의 SharePoint 프로젝트 항목을 정의하는 Visual Studio 확장 만들기.  프로젝트 항목 형식에는 **속성** 창에 표시되는 간단한 사용자 지정 속성이 포함됩니다.  
  
-   프로젝트 항목에 대한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 템플릿 만들기  
  
-   프로젝트 템플릿과 확장 어셈블리를 배포하기 위한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지 빌드  
  
-   프로젝트 항목 디버깅 및 테스트  
  
 이 연습은 독립적으로 실행할 수 있습니다.  이 연습을 완료한 후에는 프로젝트 템플릿에 마법사를 추가하여 프로젝트 항목을 개선할 수 있습니다.  자세한 내용은 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)을 참조하십시오.  
  
> [!NOTE]  
>  [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=191369](http://go.microsoft.com/fwlink/?LinkId=191369)에서 이 연습에 대한 완료된 프로젝트, 코드 및 기타 파일이 포함된 샘플을 다운로드할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows, SharePoint 및 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   SharePoint의 사이트 열.  자세한 내용은 [Columns](http://go.microsoft.com/fwlink/?LinkId=183547)를 참조하십시오.  
  
-   Visual Studio의 프로젝트 템플릿.  자세한 내용은 [Visual Studio에서 사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)을 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 세 프로젝트를 만들어야 합니다.  
  
-   VSIX 프로젝트.  이 프로젝트는 사이트 열 프로젝트 항목과 프로젝트 템플릿을 배포하기 위한 VSIX 패키지를 만듭니다.  
  
-   프로젝트 템플릿 프로젝트.  이 프로젝트는 사이트 열 프로젝트 항목이 포함된 새 SharePoint 프로젝트를 만드는 데 사용할 수 있는 프로젝트 템플릿을 만듭니다.  
  
-   클래스 라이브러리 프로젝트.  이 프로젝트는 사이트 열 프로젝트 항목의 동작을 정의하는 Visual Studio 확장을 구현합니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  **새 프로젝트** 대화 상자 상단에 **.NET Framework 4.5** 가 .NET Framework 버전의 목록에서 선택되어 있는지 확인 합니다.  
  
4.  **Visual Basic** 또는 **Visual C\#** 노드를 확장한 다음 **확장성** 노드를 선택합니다.  
  
    > [!NOTE]  
    >  **확장성** 노드는 Visual Studio 2010 SDK를 설치한 경우에만 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
5.  프로젝트 템플릿 목록에서 **VSIX 프로젝트**를 선택합니다.  
  
6.  **이름** 텍스트 상자에서 **SiteColumnProjectItem**을 입력한 다음 **확인** 버튼을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **SiteColumnProjectItem** 프로젝트를 추가합니다.  
  
#### 프로젝트 템플릿 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **솔루션** 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 새 프로젝트를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  **새 프로젝트** 대화 상자 상단에 **.NET Framework 4.5** 가 .NET Framework 버전의 목록에서 선택되어 있는지 확인 합니다.  
  
3.  **Visual C\#** 또는 **Visual Basic** 노드를 확장한 다음 **확장성** 노드를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 **C\# 프로젝트 템플릿** 또는 **Visual Basic 프로젝트 템플릿**을 선택합니다.  
  
5.  **이름** 텍스트 상자에서 **SiteColumnProjectTemplate**을 입력한 다음 **확인** 버튼을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **SiteColumnProjectTemplate** 프로젝트를 추가합니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
7.  Visual Basic 프로젝트를 만든 경우 프로젝트에서 다음 파일도 삭제합니다.  
  
    -   MyApplication.Designer.vb  
  
    -   MyApplication.myapp  
  
    -   Resources.Designer.vb  
  
    -   Resources.resx  
  
    -   Settings.Designer.vb  
  
    -   Settings.settings  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **솔루션** 노드의 바로 가기 메뉴를 열고 **추가**를 선택한 다음 새 프로젝트를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자 상단에 **.NET Framework 4.5** 가 .NET Framework 버전의 목록에서 선택되어 있는지 확인 합니다.  
  
3.  **Visual C\#** 또는 **Visual Basic** 노드를 확장하고 **Windows** 노드를 선택한 다음 **클래스 라이브러리** 템플릿을 선택합니다.  
  
4.  **이름** 텍스트 상자에서 **ProjectItemTypeDefinition** 을 입력한 다음 **확인** 버튼을 선택합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **ProjectItemTypeDefinition** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 확장 프로젝트 구성  
 코드 파일 및 어셈블리 참조를 추가하여 확장 프로젝트를 구성합니다.  
  
#### 프로젝트를 구성하려면  
  
1.  ProjectItemTypeDefinition 프로젝트에서 **SiteColumnProjectItemTypeProvider**라는 새 코드 파일을 추가합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
3.  **참조 관리자 \- ProjectItemTypeDefinition** 대화 상자에서 **어셈블리** 노드를 확장하고 **Framework** 노드를 선택한 후 System.ComponentModel.Composition 확인란을 선택합니다.  
  
4.  **확장** 노드를 선택하고, Microsoft.VisualStudio.SharePoint 어셈블리 옆에 있는 확인란을 선택한 다음 **확인** 단추를 선택합니다.  
  
## 새 SharePoint 프로젝트 항목 형식 정의  
 새 프로젝트 항목 형식의 동작을 정의하기 위해 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스를 구현하는 클래스를 만듭니다.  새 프로젝트 항목 형식을 정의하려는 경우 항상 이 인터페이스를 구현합니다.  
  
#### 새 SharePoint 프로젝트 항목 형식을 정의하려면  
  
1.  **SiteColumnProjectItemTypeProvider** 코드 파일에서 기본 코드를 다음 코드로 바꾼 다음 파일을 저장 합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/cs/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.sitecolumn/vb/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.vb#1)]  
  
## Visual Studio 프로젝트 템플릿 만들기  
 프로젝트 템플릿을 만들어서 다른 개발자가 사이트 열 프로젝트 항목이 포함된 새 SharePoint 프로젝트를 만들 수 있게 합니다.  SharePoint 프로젝트 템플릿에는 Visual Studio의 모든 프로젝트에 필요한 파일\(.csproj 또는 .vbproj\), .vstemplate 파일 및 SharePoint 프로젝트와 관련된 파일이 포함됩니다.  자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)을 참조하십시오.  
  
 이 절차에서는 SharePoint 프로젝트에 관련 된 파일을 생성하여 빈 SharePoint 프로젝트를 만들 수 있습니다.  그런 다음 이러한 파일을 SiteColumnProjectTemplate 프로젝트에 추가하여 이 프로젝트에서 생성 되는 템플릿에 포함 되어 있도록 합니다.  또한 SiteColumnProjectTemplate 프로젝트 파일을 구성하여 프로젝트 템플릿이 **새 프로젝트** 대화 상자에 나타나는 위치를 지정합니다.  
  
#### 프로젝트 템플릿의 파일을 만들려면  
  
1.  관리자 권한으로 두 번째 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 인스턴스를 시작합니다.  
  
2.  **BaseSharePointProject**라는 SharePoint 2010 프로젝트를 새로 만듭니다.  
  
    > [!IMPORTANT]  
    >  **SharePoint 사용자 지정 마법사**에서 **팜 솔루션으로 배포** 옵션 버튼을 선택하지 마십시오.  
  
3.  프로젝트에 빈 요소 항목을 추가한 다음 항목의 이름을 **Field1** 로 지정합니다.  
  
4.  프로젝트를 저장한 다음 두 번째 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 인스턴스를 닫습니다.  
  
5.  시작된 SiteColumnProjectItem 솔루션을 가진 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 인스턴스에서, **솔루션 탐색기** 에서 **SiteColumnProjectTemplate** 프로젝트 노드에 대한 바로 가기 메뉴를 열고 **추가** 를 선택한 다음 **기존 항목** 을 선택합니다.  
  
6.  **기존 항목 추가** 대화 상자에서 파일 확장명 목록을 연 다음 **모든 파일 \(\*.\*\)**을 선택합니다.  
  
7.  BaseSharePointProject 프로젝트가 포함된 디렉터리에 key.snk 파일을 선택한 다음 **추가** 버튼을 선택합니다.  
  
    > [!NOTE]  
    >  이 연습에서 만드는 프로젝트 템플릿은 이 템플릿을 사용하여 만든 각 프로젝트에 서명하는데 동일한 key.snk 파일을 사용합니다.  이 샘플을 확장하여 프로젝트 인스턴스마다 다른 key.snk 파일을 만드는 방법에 대한 자세한 내용은 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)을 참조하십시오.  
  
8.  5\-8단계를 반복하여 BaseSharePointProject 디렉터리의 지정된 하위 폴더에 있는 다음 파일을 추가합니다.  
  
    -   \\Field1\\Elements.xml  
  
    -   \\Field1\\SharePointProjectItem.spdata  
  
    -   \\Features\\Feature1\\Feature1.feature  
  
    -   \\Features\\Feature1\\Feature1.Template.xml  
  
    -   \\Package\\Package.package  
  
    -   \\Package\\Package.Template.xml  
  
     이러한 파일을 SiteColumnProjectTemplate 프로젝트에 직접 추가합니다. 프로젝트에서 Field1, Features 또는 Package 하위 폴더를 다시 만들지 마십시오.  이러한 파일에 대한 자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
#### 개발자가 새 프로젝트 대화 상자에서 프로젝트 템플릿을 검색하는 방법을 구성하려면  
  
1.  **솔루션 탐색기**에서 **SiteColumnProjectTemplate** 프로젝트 노드의 바로 가기 메뉴를 연 다음 **로드되지않은 프로젝트** 를 선택합니다.  변경 내용을 파일에 저장할지 묻는 메시지가 나타나면 **예** 버튼을 선택합니다.  
  
2.  **SiteColumnProjectTemplate** 노드의 바로 가기 메뉴를 다시 연 다음 **SiteColumnProjectTemplate.csproj 편집** 또는 **SiteColumnProjectTemplate.vbproj 편집**을 선택합니다.  
  
3.  프로젝트 파일에서 다음 `VSTemplate` 요소를 찾습니다.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
    ```  
  
4.  이 요소를 다음 XML과 같이 바꿉니다.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` 요소는 프로젝트를 빌드할 때 프로젝트 템플릿이 만들어지는 경로의 추가 폴더를 지정합니다.  여기서 지정된 폴더들은 고객이 **새 프로젝트** 대화 상자에서 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택했을 때만 프로젝트 템플릿이 유효함을 보장합니다.  
  
5.  파일을 저장한 후 닫습니다.  
  
6.  **솔루션 탐색기**에서 **SiteColumnProjectTemplate** 프로젝트의 바로 가기 메뉴를 연 다음 **프로젝트 다시 로드**를 선택합니다.  
  
## 프로젝트 템플릿 파일 편집  
 SiteColumnProjectTemplate 프로젝트의 다음 파일을 편집하여 프로젝트 템플릿의 동작을 정의합니다.  
  
-   AssemblyInfo.cs 또는 AssemblyInfo.vb  
  
-   Elements.xml  
  
-   SharePointProjectItem.spdata  
  
-   Feature1.feature  
  
-   Package.package  
  
-   SiteColumnProjectTemplate.vstemplate  
  
-   ProjectTemplate.csproj 또는 ProjectTemplate.vbproj  
  
 다음 절차에서는 바꿀 수 있는 매개 변수를 이러한 파일 중 일부에 추가합니다.  대체 가능한 매개 변수는 달러 기호\($\) 문자로 시작하고 끝나는 토큰입니다.  사용자가 이 프로젝트 템플릿을 사용하여 새 프로젝트를 만드는 경우 Visual Studio에서는 자동으로 새 프로젝트의 이러한 매개 변수를 특정 값으로 바꿉니다.  자세한 내용은 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)을 참조하십시오.  
  
#### AssemblyInfo.cs 또는 AssemblyInfo.vb 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 AssemblyInfo.cs 또는 AssemblyInfo.vb 파일 열고의 맨 위에 다음 문을 추가 합니다.  
  
    ```vb  
    Imports System.Security  
    ```  
  
    ```csharp  
    using System.Security;  
    ```  
  
     SharePoint 프로젝트의 **샌드박스 솔루션** 속성이 **True**로 설정된 경우 Visual Studio에서는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>를 AssemblyInfo 코드 파일에 추가합니다.  그러나 프로젝트 템플릿의 AssemblyInfo 코드 파일은 <xref:System.Security> 네임스페이스를 기본적으로 가져오지 않습니다.  컴파일 오류를 방지하기 위해 이 **using** 또는 **Imports** 문을 추가해야 합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### Elements.xml 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Elements.xml 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
          Name="$safeprojectname$"   
          DisplayName="$projectname$"   
          Type="Text"   
          Group="Custom Columns">  
      </Field>  
    </Elements>  
    ```  
  
     새 XML에서는 사이트 열의 이름, 기본 형식 및 갤러리에서 사이트 열을 나열할 그룹을 정의하는 `Field` 요소를 추가합니다.  이 파일의 내용에 대한 자세한 내용은 [필드 정의 스키마](http://go.microsoft.com/fwlink/?LinkId=184290) 를 참조하십시오.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### SharePointProjectItem.spdata 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 SharePointProjectItem.spdata 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <ProjectItem Type="Contoso.SiteColumn" DefaultFile="Elements.xml"   
                 xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$safeprojectname$\" Type="ElementManifest" />  
      </Files>   
    </ProjectItem>  
    ```  
  
     새 XML에서는 파일을 다음과 같이 변경합니다.  
  
    -   프로젝트 항목 정의\(이 연습의 앞부분에서 만든 `SiteColumnProjectItemTypeProvider` 클래스\)에 대한 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> 로 전달되는 동일한 문자열로 `ProjectItem` 요소의 `Type` 특성을 변경합니다.  
  
    -   `ProjectItem` 요소에서 `SupportedTrustLevels` 및 `SupportedDeploymentScopes` 특성을 제거합니다.  신뢰 수준과 배포 범위가 ProjectItemTypeDefinition 프로젝트의 `SiteColumnProjectItemTypeProvider` 클래스에 지정되기 때문에 이러한 특성 값은 필요하지 않습니다.  
  
     .spdata 파일의 내용에 대한 자세한 내용은 [SharePoint Project Item Schema Reference](../sharepoint/sharepoint-project-item-schema-reference.md)를 참조하십시오.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### Feature1.feature 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Feature1.feature 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <feature xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="$guid4$" featureId="$guid4$"   
             imageUrl="" solutionId="00000000-0000-0000-0000-000000000000" title="Site Column Feature1" version=""  
             deploymentPath="$SharePoint.Project.FileNameWithoutExtension$_$SharePoint.Feature.FileNameWithoutExtension$"  
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/FeatureModel">  
      <projectItems>  
        <projectItemReference itemId="$guid2$" />  
      </projectItems>  
    </feature>  
    ```  
  
     새 XML에서는 파일을 다음과 같이 변경합니다.  
  
    -   `feature` 요소의 `Id` 및 `featureId` 특성 값을 `$guid4$`로 변경합니다.  
  
    -   `projectItemReference` 요소의 `itemId` 특성 값을 `$guid2$`로 변경합니다.  
  
     .feature 파일에 대한 자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### Package.package 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Package.package 파일의 내용을 다음 XML로 바꿉니다.  
  
    ```  
  
    <package xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0"   
             Id="$guid3$" solutionId="$guid3$" resetWebServer="false" name="$safeprojectname$"   
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/PackageModel">  
      <features>  
        <featureReference itemId="$guid4$" />  
      </features>  
    </package>  
    ```  
  
     새 XML에서는 파일을 다음과 같이 변경합니다.  
  
    -   `package` 요소의 `Id` 및 `solutionId` 특성 값을 `$guid3$`로 변경합니다.  
  
    -   `featureReference` 요소의 `itemId` 특성 값을 `$guid4$`로 변경합니다.  
  
     .package 파일에 대한 자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### SiteColumnProjectTemplate.vstemplate 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 SiteColumnProjectTemplate.vstemplate 파일의 내용을 다음 XML 섹션 중 하나를 사용하여 바꿉니다.  
  
    -   Visual C\# 프로젝트 템플릿을 만드는 경우에는 다음 XML을 사용합니다.  
  
    ```  
  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>CSharp</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.csproj" File="ProjectTemplate.csproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
    -   Visual Basic 프로젝트 템플릿을 만드는 경우에는 다음 XML을 사용합니다.  
  
    ```  
  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>VisualBasic</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.vbproj" File="ProjectTemplate.vbproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="My Project\AssemblyInfo.vb">AssemblyInfo.vb</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     새 XML에서는 파일을 다음과 같이 변경합니다.  
  
    -   `Name` 요소를 **사이트 열** 값으로 설정합니다. \(이러한 항목은 **새 프로젝트** 대화 상자에 나타납니다.\)  
  
    -   각 프로젝트 인스턴스에 포함된 각 파일에 대한 `ProjectItem` 요소를 추가합니다.  
  
    -   "http:\/\/schemas.microsoft.com\/developer\/vstemplate\/2005" 네임 스페이스를 사용합니다.  이 솔루션의 다른 프로젝트 파일 "http:\/\/schemas.microsoft.com\/developer\/msbuild\/2003" 네임 스페이스를 사용 합니다.  따라서 XML 스키마 경고 메시지가 생성 되지만, 이 연습에서는 무시할 수 있습니다.  
  
     .vstemplate 파일의 내용에 대한 자세한 내용은 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)를 참조하십시오.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### ProjectTemplate.csproj 또는 ProjectTemplate.vbproj 파일을 편집하려면  
  
1.  SiteColumnProjectTemplate 프로젝트의 ProjectTemplate.csproj 파일 또는 ProjectTemplate.vbproj 파일의 내용을 다음 XML 섹션 중 하나를 사용하여 바꿉니다.  
  
    -   Visual C\# 프로젝트 템플릿을 만드는 경우에는 다음 XML을 사용합니다.  
  
    ```  
  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <AppDesignerFolder>Properties</AppDesignerFolder>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{14822709-B5A1-4724-98CA-57A101D1B079};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineConstants>DEBUG;TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <DefineConstants>TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Web" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="Properties\AssemblyInfo.cs" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
    1.  Visual Basic 프로젝트 템플릿을 만드는 경우에는 다음 XML을 사용합니다.  
  
    ```  
  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProductVersion>  
        </ProductVersion>  
        <SchemaVersion>  
        </SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{D59BE175-2ED0-4C54-BE3D-CDAA9F3214C8};{F184B08F-C81C-45F6-A57F-5ABD9991F28F}</ProjectTypeGuids>  
        <OptionExplicit>On</OptionExplicit>  
        <OptionCompare>Binary</OptionCompare>  
        <OptionStrict>Off</OptionStrict>  
        <OptionInfer>On</OptionInfer>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <OutputPath>bin\Debug\</OutputPath>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <DefineDebug>false</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Import Include="Microsoft.VisualBasic" />  
        <Import Include="System" />  
        <Import Include="System.Collections" />  
        <Import Include="System.Collections.Generic" />  
        <Import Include="System.Data" />  
        <Import Include="System.Diagnostics" />  
        <Import Include="System.Linq" />  
        <Import Include="System.Xml.Linq" />  
        <Import Include="Microsoft.SharePoint" />  
        <Import Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="My Project\AssemblyInfo.vb" />  
      </ItemGroup>  
      <ItemGroup>  
        <AppDesigner Include="My Project\" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
     새 XML에서는 파일을 다음과 같이 변경합니다.  
  
    -   `TargetFrameworkVersion` 요소를 사용하여 .NET Framework 4.5가 아닌 3.5를 지정합니다.  
  
    -   프로젝트 출력에 서명할 `SignAssembly` 및 `AssemblyOriginatorKeyFile` 요소를 추가합니다.  
  
    -   SharePoint 프로젝트에서 사용하는 어셈블리 참조에 대한 `Reference` 요소를 추가합니다.  
  
    -   Elements.xml 및 SharePointProjectItem.spdata와 같은 프로젝트의 각 기본 파일에 대한 요소를 추가합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## 프로젝트 템플릿을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 **SiteColumnProjectItem** 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  먼저 VSIX 프로젝트에 포함된 source.extension.vsixmanifest 파일을 수정하여 VSIX 패키지를 구성합니다.  그런 다음 솔루션을 빌드하여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하고 만들려면  
  
1.  **솔루션 탐색기**에서 **SiteColumnProjectItem** 프로젝트의 source.extension.vsixmanifest 파일을 엽니다.  
  
     source.extension.vsixmanifest 파일은 모든 VSIX 패키지에 필요한 extension.vsixmanifest 파일의 기초를 제공합니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  **제품 이름** 상자에 **사이트 열**을 입력합니다.  
  
3.  **만든 이** 상자에 **Contoso**를 입력합니다.  
  
4.  **설명** 상자에 **사이트 열을 만들기 위한 SharePoint 프로젝트**를 입력합니다.  
  
5.  **자산** 탭을 선택한 다음 **새로 만들기** 버튼을 선택합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
6.  **유형** 목록에서, **Microsoft.VisualStudio.ProjectTemplate**를 선택합니다.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `ProjectTemplate` 요소에 해당합니다.  이 요소는 프로젝트 템플릿이 포함된 VSIX 패키지의 하위 폴더를 식별합니다.  자세한 내용은 [NIB: ProjectTemplate Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/87add64c-9dcd-495f-8815-209dab182cb1)을 참조하십시오.  
  
7.  **원본** 목록에서 **현재 솔루션의 프로젝트**를 선택합니다.  
  
8.  **프로젝트** 목록에서 **SiteColumnProjectTemplate**를 선택한 다음 **확인** 버튼을 선택합니다.  
  
9. **새로 만들기** 버튼을 선택합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
10. **유형** 목록에서, **Microsoft.VisualStudio.MefComponent**를 선택합니다.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
11. **원본** 목록에서 **현재 솔루션의 프로젝트**를 선택합니다.  
  
12. **프로젝트** 목록에서 **ProjectItemTypeDefinition**를 선택한 다음 **확인** 버튼을 선택합니다.  
  
13. 선택 메뉴 모음에서, **빌드**, **솔루션 빌드**를 선택하여 프로젝트가 오류없이 컴파일되는지 확인합니다.  
  
## 프로젝트 템플릿 테스트  
 이제 프로젝트 템플릿을 테스트할 준비가 되었습니다.  우선 실험 모드의 Visual Studio 인스턴스에서 SiteColumnProjectItem 솔루션 디버깅을 시작합니다.  그런 다음 실험 모드의 Visual Studio 인스턴스에서 **사이트 열** 프로젝트를 테스트합니다.  마지막으로, SharePoint 프로젝트를 빌드 및 실행하여 사이트 열이 예상대로 작동하는지 확인합니다.  
  
#### 솔루션 디버깅을 시작하려면  
  
1.  관리자 권한으로 Visual Studio를 다시 시작한 다음 SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  SiteColumnProjectItemTypeProvider 코드 파일에서, `InitializeType` 메서드에서 코드의 첫 번째 줄에 중단점을 추가한 다음 **F5** 키를 눌러 디버깅을 시작합니다.  
  
     Visual Studio에서는 확장을 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\10.0Exp\\Extensions\\Contoso\\Site Column\\1.0에 설치하고 실험 모드의 Visual Studio 인스턴스를 시작합니다.  이 Visual Studio 인스턴스에서 프로젝트 항목을 테스트합니다.  
  
#### Visual Studio에서 프로젝트를 테스트하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 메뉴 바의 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  프로젝트 템플릿에서 지원하는 언어에 따라 **Visual C\#** 또는 **Visual Basic** 노드를 확장하고 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  프로젝트 템플릿 목록에서 **사이트 열** 템플릿을 선택합니다.  
  
4.  **이름** 상자에서 **SiteColumnTest** 를 입력한 다음 **확인** 버튼을 선택합니다.  
  
     새 프로젝트가 **Field1**이라는 프로젝트 항목과 함께 **솔루션 탐색기**에 나타납니다.  
  
5.  Visual Studio의 다른 인스턴스에서 코드가 이전에 `InitializeType` 메서드에서 설정한 중단점에서 중지하는지 확인한 다음, **F5** 키를 눌러 프로젝트 디버깅을 계속합니다.  
  
6.  **솔루션 탐색기** 에서, **Field1** 노드를 선택한 다음 **F4** 키를 누릅니다.  
  
     **속성** 창이 열립니다.  
  
7.  **Example Property** 속성이 속성 목록에 나타나는지 확인합니다.  
  
#### SharePoint에서 사이트 열을 테스트하려면  
  
1.  **솔루션 탐색기**에서 **SiteColumnTest** 노드를 선택합니다.  
  
2.  **속성** 창에서 **사이트 URL** 속성 옆의 텍스트 상자를 클릭하고 **http:\/\/localhost**를 입력합니다.  
  
     이 단계는 디버깅에 사용할 개발 컴퓨터의 로컬 SharePoint 사이트를 지정합니다.  
  
    > [!NOTE]  
    >  프로젝트가 만들어질 때 사이트 열 프로젝트 템플릿이 이 값을 수집하기 위한 마법사를 제공하지 않기 때문에 **사이트 URL** 속성은 기본적으로 비어 있습니다.  개발자에게 이 값을 물은 다음 새 프로젝트에서 이 속성을 구성하는 마법사를 추가하는 방법에 대한 자세한 내용은 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)를 참조하십시오.  
  
3.  **F5** 키를 선택합니다.  
  
     사이트 열이 패키지되어 프로젝트의 **사이트 URL** 속성에 지정된 SharePoint 사이트로 배포됩니다.  이 사이트의 기본 페이지가 웹 브라우저에서 열립니다.  
  
    > [!NOTE]  
    >  **스크립트 디버깅 사용 안 함** 대화 상자가 표시되면 **예** 단추를 선택하여 프로젝트를 계속 디버깅합니다.  
  
4.  **사이트 동작** 메뉴에서 **사이트 설정**을 선택합니다.  
  
5.  **사이트 설정** 페이지의 **갤러리** 리스트에서 **사이트 열** 링크를 선택합니다.  
  
6.  사이트 열의 목록에서 **SiteColumnTest**라는 열이 포함된 **사용자 지정 열** 그룹이 있는지 확인합니다.  
  
7.  웹 브라우저를 닫습니다.  
  
## 개발 컴퓨터 정리  
 프로젝트의 테스트를 마쳤으면 실험 모드의 Visual Studio 인스턴스에서 프로젝트 템플릿을 제거합니다.  
  
#### 개발 컴퓨터를 정리하려면  
  
1.  실험 모드의 Visual Studio 인스턴스에서 **도구** 메뉴의 **확장 및 업데이트**를 선택합니다.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장 목록에서 **사이트 열** 확장자를 선택한 다음 **제거** 버튼을 선택합니다.  
  
3.  나타나는 대화 상자에서 **예** 단추를 선택하여 확장을 제거합니다.  
  
4.  **닫기** 단추를 선택하여 삭제작업을 완료합니다.  
  
5.  Visual Studio의 두 인스턴스, 즉 실험 모드의 인스턴스와 SiteColumnProjectItem 솔루션이 열려 있는 Visual Studio 인스턴스를 모두 닫습니다.  
  
## 다음 단계  
 이 연습을 완료한 후에는 프로젝트 템플릿에 마법사를 추가할 수 있습니다.  사용자가 사이트 열 프로젝트를 만들 때 마법사에서는 사용자에게 디버깅에 사용할 사이트 URL과 새 솔루션에 샌드박스가 적용되는지 여부를 묻고 이 정보를 사용하여 새 프로젝트를 구성합니다.  또한 마법사에서는 열에 대한 정보\(예: 기본 형식 및 사이트 열 갤러리에서 열을 나열할 그룹\)를 수집하고 이 정보를 새 프로젝트의 Elements.xml 파일에 추가합니다.  자세한 내용은 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)을 참조하십시오.  
  
## 참고 항목  
 [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Associating Custom Data with SharePoint Tools Extensions](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  