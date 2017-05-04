---
title: "Deploying Extensions for the SharePoint Tools in Visual Studio | Microsoft Docs"
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
  - "SharePoint development in Visual Studio, deploying extensions"
ms.assetid: 69927d95-acdf-4fd8-ac43-28e9a7fa8a38
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# Deploying Extensions for the SharePoint Tools in Visual Studio
  SharePoint 도구 확장을 배포하려면 확장 어셈블리 및 확장과 함께 배포할 다른 모든 파일이 포함된 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  VSIX 패키지는 OPC\(Open Packaging Conventions\) 표준을 따르는 압축 파일입니다.  VSIX 패키지의 확장명은 .vsix입니다.  
  
 VSIX 패키지를 만든 후에는 다른 사용자가 .vsix 파일을 실행하여 확장을 설치할 수 있습니다.  사용자가 확장을 설치하면 모든 파일이 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0\\Extensions 폴더에 설치됩니다.  확장을 배포하려면 VSIX 패키지를 [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트에 업로드하거나 네트워크 공유 또는 다른 웹 사이트에서 패키지를 호스팅하는 등의 다른 방법으로 패키지를 고객에게 배포할 수 있습니다.  
  
 VSIX 패키지를 만들어 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847)에 배포하는 방법에 대한 자세한 내용은 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)를 참조하십시오.  
  
 VSIX 패키지는 Visual Studio의 **VSIX 프로젝트** 템플릿을 사용하여 만들거나 수동으로 만들 수 있습니다.  
  
## VSIX 프로젝트를 사용하여 VSIX 패키지 만들기  
 Visual Studio SDK에서 제공하는 **VSIX 프로젝트** 템플릿을 사용하여 SharePoint 도구 확장용 VSIX 패키지를 만들 수 있습니다.  VSIX 프로젝트를 사용하면 수동으로 VSIX 패키지를 만들 때보다 다음과 같은 여러 가지 이점이 있습니다.  
  
-   프로젝트를 빌드할 때 VSIX 패키지가 자동으로 생성됩니다.  패키지에 배포 파일을 추가하고 패키지에 사용할 \[Content\_Types\].xml 파일을 만드는 등의 작업이 자동으로 수행됩니다.  
  
-   확장 프로젝트와 프로젝트 템플릿 및 항목 템플릿과 같은 기타 파일의 빌드 출력을 VSIX 패키지에 포함하도록 VSIX 프로젝트를 구성할 수 있습니다.  
  
 VSIX 프로젝트를 사용하는 방법에 대한 자세한 내용은 [VSIX 프로젝트 템플릿](../extensibility/vsix-project-template.md)를 참조하십시오.  
  
### 프로젝트 구성  
 기본적으로 VSIX 프로젝트는 VSIX 패키지만 생성하고 어셈블리는 생성하지 않습니다.  따라서 VSIX 프로젝트에서는 대개 SharePoint 도구 확장을 구현하지 않습니다.  일반적으로 적어도 다음 두 프로젝트로 작업합니다.  
  
-   VSIX 프로젝트  
  
-   확장을 구현하는 클래스 라이브러리 프로젝트  
  
 특정 유형의 확장에 대해 추가 프로젝트로 작업할 수도 있습니다.  
  
-   확장에서 사용하는 모든 SharePoint 명령을 구현하는 클래스 라이브러리 프로젝트.  이 시나리오를 보여 주는 연습은 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)를 참조하십시오.  
  
-   확장에서 새로운 형식의 SharePoint 프로젝트 항목을 정의하는 경우 항목 템플릿이나 프로젝트 템플릿을 만드는 항목 템플릿 또는 프로젝트 템플릿 프로젝트.  이 시나리오를 보여 주는 연습은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)를 참조하십시오.  
  
-   확장에 템플릿이 포함된 경우 항목 템플릿 또는 프로젝트 템플릿에 대한 사용자 지정 마법사를 구현하는 클래스 라이브러리 프로젝트.  이 시나리오를 보여 주는 연습은 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)를 참조하십시오.  
  
 모든 프로젝트를 같은 Visual Studio 솔루션에 포함하는 경우 VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 수정하여 클래스 라이브러리 프로젝트의 빌드 출력을 포함할 수 있습니다.  
  
### VSIX 매니페스트 편집  
 VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 편집하여 확장에 포함할 모든 항목에 대한 항목을 포함해야 합니다.  해당 바로 가기 메뉴에서 source.extension.vsixmanifest 파일을 열면 파일에 XML을 편집할 수 있는 UI를 제공 하는 디자이너 파일이 나타납니다.  자세한 내용은 [VSIX 매니페스트 디자이너](../extensibility/media/vsix-manifest-designer.png)을 참조하십시오.  
  
 source.extension.vsixmanifest 파일에 다음 항목에 대한 항목을 추가해야 합니다.  
  
-   확장 어셈블리  
  
-   확장에서 사용하는 모든 SharePoint 명령을 구현하는 어셈블리  
  
-   확장과 연결된 모든 프로젝트 템플릿 또는 항목 템플릿  
  
-   확장과 연결된 템플릿에 대한 사용자 지정 마법사  
  
 다음 절차에서는 이러한 각 항목에 대한 .vsixmanifest 파일에 항목을 추가하는 방법에 대해 설명합니다.  
  
##### 확장 어셈블리를 포함하려면  
  
1.  VSIX 프로젝트를 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택  **열기**.  
  
     디자이너에서 파일을 엽니다.  
  
2.  에  **자산** 탭 편집기의 선택은  **New** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 열립니다.  
  
3.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.MefComponent**.  
  
4.  에  **소스** 목록에서 다음 단계 중 하나를 수행 하십시오.  
  
    -   확장 어셈블리가 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트에서 빌드된 경우 선택  **는 프로젝트를 현재 솔루션**.  에 있는  **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   확장 어셈블리가 프로젝트에 파일로 포함 되어 있는 경우 선택  **파일 시스템에 파일을**.  에  **경로** 목록, 확장 어셈블리 파일에 전체 경로 입력 하거나 사용 된  **찾아보기** 찾아 어셈블리 파일을 선택 하려면 단추.  
  
5.  **확인** 단추를 선택합니다.  
  
##### SharePoint 명령 어셈블리를 포함하려면  
  
1.  VSIX 프로젝트를 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택 된  **열기** 단추.  
  
     파일이 디자이너에서 열립니다.  
  
2.  에  **자산** 섹션 편집기의 선택은  **새** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 열립니다.  
  
3.  에 있는  **유형** 상자에 입력  **SharePoint.Commands.v4**.  
  
4.  에  **소스** 목록에서 다음 단계 중 하나를 수행 하십시오.  
  
    -   명령 어셈블리가 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트에서 빌드된 경우 선택  **는 프로젝트를 현재 솔루션**.  에 있는  **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   명령 어셈블리가 프로젝트에 파일로 포함 되어 있는 경우 선택  **파일 시스템에 파일을**.  에  **경로** 목록, 확장 어셈블리 파일에 전체 경로 입력 하거나 사용 된  **찾아보기** 찾아 어셈블리 파일을 선택 하려면 단추.  
  
5.  **확인** 단추를 선택합니다.  
  
##### 사용자가 만든 서식 파일을 포함 하려면  
  
1.  VSIX 프로젝트를 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택 된  **열기** 단추.  
  
     파일이 디자이너에서 열립니다.  
  
2.  에  **자산** 섹션 편집기의 선택은  **새** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 열립니다.  
  
3.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.ProjectTemplate** 또는  **Microsoft.VisualStudio.ItemTemplate**.  
  
4.  에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
5.  에  **프로젝트** 목록에서 프로젝트의 이름을 선택 하 고 다음 선택은  **확인** 단추.  
  
6.  **솔루션 탐색기**프로젝트 템플릿 또는 항목 템플릿 프로젝트에 대 한 바로 가기 메뉴를 열고 선택  **프로젝트 언로드**.  
  
7.  프로젝트 노드에 대 한 바로 가기 메뉴를 다시 열고 선택  **편집***YourTemplateProjectName***.csproj** 또는  **편집***YourTemplateProjectName***.vbproj**.  
  
8.  프로젝트 파일에서 다음 `VSTemplate` 요소를 찾습니다.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
    ```  
  
9. 이 요소를 다음 XML로 바꿉니다.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` 요소는 프로젝트를 빌드할 때 프로젝트 템플릿이 만들어지는 경로의 추가 폴더를 지정합니다.  여기에 지정 된 폴더 고객 열면 항목 템플릿을 사용할 수 있게는  **새 프로젝트 추가** 대화 상자에서 확장은  **SharePoint** 노드를 다음 선택은  **2010** 노드.  
  
10. 파일을 저장한 후 닫습니다.  
  
11. **솔루션 탐색기**프로젝트 템플릿 또는 항목 템플릿 프로젝트에 대 한 바로 가기 메뉴를 열고 선택  **프로젝트 다시 로드**.  
  
##### 수동으로 만든 템플릿을 포함하려면  
  
1.  VSIX 프로젝트에서 템플릿이 포함될 프로젝트에 새 폴더를 추가합니다.  
  
2.  이 새 폴더 아래에 다음 하위 폴더를 만든 다음 *Locale ID* 폴더에 템플릿 파일\(.zip\)을 추가합니다.  
  
     *YourTemplateFolder*  
  
     **SharePoint**  
  
     **SharePoint14**  
  
     *Locale ID*  
  
     *YourTemplateName*.zip  
  
     예를 들어 영어\(미국\) 로캘을 지원하는 ContosoCustomAction.zip이라는 항목 템플릿이 있는 경우 전체 경로는 ItemTemplates\\SharePoint\\SharePoint14\\1033\\ContosoCustomAction.zip일 수 있습니다.  
  
3.  **솔루션 탐색기**, 템플릿 파일을 선택 \(*YourTemplateName*.zip\).  
  
4.  **속성** 창에서 **빌드 작업** 속성을 **콘텐츠**로 설정합니다.  
  
5.  Source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택  **열기**.  
  
     파일이 디자이너에서 열립니다.  
  
6.  에  **자산** 섹션 편집기의 선택은  **새** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 열립니다.  
  
7.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.ItemTemplate** 또는  **Microsoft.VisualStudio.ProjectTemplate**.  
  
8.  에  **원본** 목록에서 선택  **파일 시스템에 파일을**.  
  
9. 에  **경로** 필드에서 어셈블리 전체 경로 입력 \(예를 들어,  **ItemTemplates\\SharePoint\\SharePoint14\\1033\\ContosoCustomAction.zip**, 또는 사용은  **찾아보기** 단추를 찾아 어셈블리를 선택 하 고 선택의  **확인** 단추.  
  
##### 프로젝트 템플릿 또는 항목 템플릿에 대한 마법사를 포함하려면  
  
1.  VSIX 프로젝트를 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택  **열기**.  
  
     파일이 디자이너에서 열립니다.  
  
2.  에  **자산** 섹션 편집기의 선택은  **새** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 열립니다.  
  
3.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.Assembly**.  
  
4.  에  **소스** 목록에서 다음 단계 중 하나를 수행 하십시오.  
  
    -   마법사 어셈블리가 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트에서 빌드된 경우 선택  **는 프로젝트를 현재 솔루션**.  에 있는  **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   마법사 어셈블리가 프로젝트에 파일로 포함 되는 경우 선택  **파일 시스템에 파일을**.  에  **경로** 필드, 어셈블리 파일에 전체 경로 입력 하거나 사용 된  **찾아보기** 단추를 찾아 어셈블리를 선택 합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
### 관련 연습  
 다음 표에는 VSIX 프로젝트를 사용하여 다양한 형식의 SharePoint 도구 확장을 배포하는 방법을 보여 주는 연습이 나와 있습니다.  
  
|확장 형식|관련 연습|  
|-----------|-----------|  
|확장 어셈블리만 포함된 확장|[Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)<br /><br /> [Walkthrough: Creating a SharePoint Project Extension](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)<br /><br /> [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)|  
|SharePoint 명령이 포함된 확장|[Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)<br /><br /> [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
|Visual Studio 템플릿이 포함된 확장|[Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)|  
|템플릿 마법사가 포함된 확장|[Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
  
## 수동으로 VSIX 패키지 만들기  
 SharePoint 도구 확장용 VSIX 패키지를 수동으로 만들려는 경우 다음 단계를 수행합니다.  
  
1.  extension.vsixmanifest 파일, \[Content\_Types\].xml 및 VSIX 패키지 파일\(.vsix 파일\)을 만듭니다.  자세한 내용은 [VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md) 및 [방법: 수동으로 확장 패키지&#40;VSIX 배포&#41;](~/misc/how-to-manually-package-an-extension-vsix-deployment.md)를 참조하십시오.  
  
2.  VSIX 패키지에 확장 어셈블리를 추가합니다.  확장에 SharePoint 명령이 포함되어 있으면 SharePoint 명령을 구현하는 어셈블리도 VSIX 패키지에 추가합니다.  
  
3.  extension.vsixmanifest 파일을 수정합니다.  
  
    -   추가 `Microsoft.VisualStudio.MefComponent` 요소는 `Assets` 요소로 설정한 다음 VSIX 패키지에 확장을 구현 하는 어셈블리의 상대 경로 새 요소의 값입니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
    -   추가 확장에 대 한 SharePoint 서버 개체 모델을 호출 하는 SharePoint 명령을 포함 하는 경우는 `Microsoft.VisualStudio.Assembly` 요소는 `Assets` 요소.  새 요소의 값을 VSIX 패키지에서 SharePoint 명령을 구현 하는 어셈블리의 상대 경로로 설정 합니다.  자세한 내용은 [자산 요소 \(VSX 스키마\)](http://msdn.microsoft.com/ko-kr/9fcfc098-edc7-484b-9d4c-acd17829d737)을 참조하십시오.  
  
    -   확장 프로젝트 템플릿 또는 항목 템플릿을 포함 하는 경우 추가 `ProjectTemplate` 또는 `ItemTemplate` 요소는 `Assets` 요소.  새 요소의 값을 VSIX 패키지에서 템플릿이 포함 된 폴더의 상대 경로로 설정 합니다.  자세한 내용은 [NIB: ProjectTemplate Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/87add64c-9dcd-495f-8815-209dab182cb1) 및 [NIB: ItemTemplate Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/1d489e54-c1c5-4f96-a510-6c2640867ff0)를 참조하십시오.  
  
    -   프로젝트 템플릿 또는 항목 템플릿에 대 한 사용자 지정 마법사 확장을 포함 하는 경우 추가 된 `Assembly` 요소 아래는 `Assets` 요소.  새 요소 값을 VSIX 패키지에 있는 어셈블리의 상대 경로로 설정한 다음 설정 된 `AssemblyName` 특성 \(버전, culture 및 공개 키 토큰 포함\) 전체 어셈블리 이름으로.  자세한 내용은 [종속성 요소 \(VSX 스키마\)](http://msdn.microsoft.com/ko-kr/1f63f60a-98ad-48ec-8e44-4eba383d3e37)을 참조하십시오.  
  
### 예제  
 다음 예제에서는 SharePoint 도구 확장에 대한 extension.vsixmanifest 파일의 내용을 보여 줍니다.  확장 Contoso.ProjectExtension.dll 라는 어셈블리에 구현 됩니다.  확장 하 고 Contoso.ExtensionCommands.dll 라는 폴더 아래의 항목 템플릿을 이라는 SharePoint 명령 어셈블리가 포함  **ItemTemplates** VSIX 패키지에서입니다.  이 예제에서는 두 어셈블리 모두 VSIX 패키지의 extension.vsixmanifest 파일과 동일한 폴더에 있다고 가정합니다.  
  
```  
<PackageManifest Version=”2.0.0” xmlns=”http://schemas.microsoft.com/developer/vsx-schema/2011”>  
  <Metadata>  
    <Identity Id="CustomActionProjectItem.Microsoft.b99efe4d-cef3-4afd-b9af-034ca0c52743" Version="1.0" Language="en-US" Publisher="Microsoft" />  
    <DisplayName>CustomActionProjectItem</DisplayName>  
    <Description>Empty VSIX Project.</Description>  
  </Metadata>  
  <Installation>  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="11.0" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" Version="4.5" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.ItemTemplate" Path="ItemTemplates" />  
    <Asset Type="Microsoft.VisualStudio.MefComponent" Path="ProjectItemDefinition.dll" />  
  </Assets>  
</PackageManifest>  
  
```  
  
## 참고 항목  
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Debugging Extensions for the SharePoint Tools in Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  