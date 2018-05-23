---
title: Visual Studio에서 SharePoint 도구에 대 한 확장 배포 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying extensions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a7ed6b037d04e867b2d94a28fef5ecb6760e39dc
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="deploying-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Visual Studio에서 SharePoint 도구에 대한 확장명 배포
  SharePoint 도구 확장을 배포 하려면 만들기를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장 프로그램 어셈블리 및 다른 모든 파일 확장명으로 배포 하려면에 포함 된 (VSIX) 확장 패키지입니다. VSIX 패키지는 압축된 된 파일을 열고 패키징 규칙 (OPC) 표준을 따릅니다. VSIX 패키지는.vsix 확장을 포함합니다.  
  
 VSIX 패키지를 만든 후 다른 사용자가 확장을 설치 하려면.vsix 파일을 실행할 수 있습니다. 사용자 확장 프로그램을 설치 하는 경우 모든 파일 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions 폴더에 설치 됩니다. 확장을 배포 하려면 VSIX 패키지를 업로드할 수 있습니다는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트 또는 있습니다 패키지에 배포할 수 고객에 게 네트워크 공유 나 일부 다른 웹 사이트에 패키지를 호스트 하는 등의 다른 방법으로 합니다.  
  
 VSIX 패키지 만들기 및 배포에 대 한 자세한 내용은 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847), 참조 [Visual Studio 확장명 전달](/visualstudio/extensibility/shipping-visual-studio-extensions)합니다.  
  
 사용 하 여 VSIX 패키지를 만들 수는 **VSIX 프로젝트** Visual Studio에서 템플릿을 VSIX 패키지를 수동으로 만들 수 있습니다.  
  
## <a name="using-vsix-projects-to-create-vsix-packages"></a>VSIX 프로젝트를 사용 하 여 VSIX 패키지 만들기  
 사용할 수는 **VSIX 프로젝트** 템플릿 패키지를 만드는 VSIX SharePoint 도구 확장에 대 한 Visual Studio SDK에서 제공 합니다. VSIX 프로젝트를 사용 하 여 VSIX 패키지를 수동으로 만드는 여러 가지 이점을 제공 합니다.  
  
-   프로젝트를 빌드할 때 visual Studio는 VSIX 패키지를 자동으로 생성 합니다. 패키지에 배포 파일을 추가 하 고 패키지에 대 한 [Content_Types].xml 파일을 만드는 등의 작업 수행 됩니다.  
  
-   VSIX 패키지의 확장 프로그램 프로젝트 및 프로젝트 템플릿 및 항목 템플릿 등의 기타 파일의 빌드 출력을 포함 하도록 VSIX 프로젝트를 구성할 수 있습니다.  
  
 VSIX 프로젝트를 사용 하는 방법에 대 한 자세한 내용은 참조 [VSIX 프로젝트 템플릿은](/visualstudio/extensibility/vsix-project-template)합니다.  
  
### <a name="organizing-your-projects"></a>프로젝트 구성  
 기본적으로 VSIX 프로젝트는 어셈블리는 아님 VSIX 패키지를 생성합니다. 따라서 일반적으로 구현 하지 않으면 SharePoint 도구 확장의 VSIX 프로젝트. 일반적으로 두 개 이상의 프로젝트와 함께 작동합니다.  
  
-   VSIX 프로젝트입니다.  
  
-   확장을 구현 하는 클래스 라이브러리 프로젝트.  
  
 작업할 수도 있습니다 추가 프로젝트와 함께 특정 확장 프로그램:  
  
-   확장 프로그램에서 사용 되는 모든 SharePoint 명령을 구현 하는 클래스 라이브러리 프로젝트. 이 시나리오를 보여 주는 연습을 참조 하십시오. [연습: 디스플레이 웹 파트를 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다.  
  
-   확장 프로그램 새 형식의 SharePoint 프로젝트 항목을 정의 하는 경우 프로젝트 템플릿 또는 항목 템플릿을 만드는 프로젝트 템플릿 또는 항목 템플릿을 프로젝트입니다. 이 시나리오를 보여 주는 연습을 참조 하십시오. [연습: 항목 템플릿, 1 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)합니다.  
  
-   확장 프로그램에 템플릿을 포함 하는 경우 항목 템플릿 또는 서식 파일 프로젝트에 대 한 사용자 지정 마법사를 구현 하는 클래스 라이브러리 프로젝트. 이 시나리오를 보여 주는 연습을 참조 하십시오. [연습: 항목 템플릿, 2 부를 사용 하 여 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)합니다.  
  
 같은 Visual Studio 솔루션의 모든 프로젝트를 포함 하는 경우 클래스 라이브러리 프로젝트의 빌드 출력을 포함 하도록 VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 수정할 수 있습니다.  
  
### <a name="editing-the-vsix-manifest"></a>VSIX 매니페스트 편집  
 확장 프로그램에 포함할 수 있는 모든 항목에 대 한 항목을 포함 하려면 VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 편집 해야 합니다. 바로 가기 메뉴에서 source.extension.vsixmanifest 파일을 열 때 파일에서 XML을 편집 하기 위한 UI를 제공 하는 디자이너에는 파일이 나타납니다. 자세한 내용은 참조 [VSIX 매니페스트 디자이너](/visualstudio/extensibility/vsix-manifest-designer)합니다.  
  
 다음 항목에 대 한 source.extension.vsixmanifest 파일에 항목을 추가 해야 합니다.  
  
-   확장 프로그램 어셈블리입니다.  
  
-   확장 프로그램에서 사용 되는 모든 SharePoint 명령을 구현 하는 어셈블리입니다.  
  
-   모든 프로젝트 템플릿 또는 연결 된 확장 프로그램 항목 템플릿  
  
-   확장 프로그램에 연결 하는 서식 파일에 대 한 사용자 지정 마법사.  
  
 다음 절차는 이러한 각 항목에 대 한.vsixmanifest 파일에 항목을 추가 하는 방법을 설명 합니다.  
  
##### <a name="to-include-the-extension-assembly"></a>확장 프로그램 어셈블리를 포함 하려면  
  
1.  VSIX 프로젝트에서 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다.  
  
     디자이너에서 파일이 열립니다.  
  
2.  에 **자산** 탭 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
4.  에 **소스** 목록에서 다음 단계 중 하나를 수행 합니다.  
  
    -   확장 프로그램 어셈블리를 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트에서 빌드한 경우 선택 **현재 솔루션의 프로젝트**합니다. 에 **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   확장 프로그램 어셈블리를 프로젝트에 파일로 포함할 경우 선택 **파일 시스템의 파일**합니다. 에 **경로** 목록 확장 프로그램 어셈블리 파일 전체 경로를 입력 하거나 사용 하 여는 **찾아보기** 단추를 찾아 어셈블리 파일을 선택 합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
##### <a name="to-include-a-sharepoint-command-assembly"></a>SharePoint 명령 어셈블리를 포함 하려면  
  
1.  VSIX 프로젝트에서 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택한 후는 **열고** 단추입니다.  
  
     파일이는 디자이너에서 열립니다.  
  
2.  에 **자산** 섹션 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  에 **형식** 상자에 입력 **SharePoint.Commands.v4**합니다.  
  
4.  에 **소스** 목록에서 다음 단계 중 하나를 수행 합니다.  
  
    -   선택 명령 어셈블리에서 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트를 빌드할 경우 **현재 솔루션의 프로젝트**합니다. 에 **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   명령 어셈블리가 파일로 프로젝트에 포함 되 면 선택 **파일 시스템의 파일**합니다. 에 **경로** 목록 확장 프로그램 어셈블리 파일 전체 경로를 입력 하거나 사용 하 여는 **찾아보기** 단추를 찾아 어셈블리 파일을 선택 합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
##### <a name="to-include-a-template-that-you-create"></a>만든 서식 파일을 포함 하려면  
  
1.  VSIX 프로젝트에서 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택한 후는 **열고** 단추입니다.  
  
     파일이는 디자이너에서 열립니다.  
  
2.  에 **자산** 섹션 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.ProjectTemplate** 또는 **Microsoft.VisualStudio.ItemTemplate**합니다.  
  
4.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
5.  에 **프로젝트** 나열 하는 프로젝트의 이름을 선택한 다음 선택에서 **확인** 단추입니다.  
  
6.  **솔루션 탐색기**, 프로젝트 템플릿 또는 항목 템플릿을 프로젝트에 대 한 바로 가기 메뉴를 열고 선택한 후 **프로젝트 언로드**합니다.  
  
7.  프로젝트 노드에 대 한 바로 가기 메뉴를 다시 연 다음 선택 **편집***YourTemplateProjectName***.csproj** 또는 **편집***YourTemplateProjectName***합니다. vbproj**합니다.  
  
8.  다음 찾기 `VSTemplate` 프로젝트 파일의 요소입니다.  
  
    ```xml  
    <VSTemplate Include="YourTemplateName.vstemplate">  
    ```  
  
9. 이 요소를 다음 XML로 바꿉니다.  
  
    ```xml  
    <VSTemplate Include="YourTemplateName.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` 요소 프로젝트를 빌드할 때 프로젝트 템플릿이 생성 되었는지 경로에 추가 폴더를 지정 합니다. 여기에 지정 된 폴더는 고객 열면 항목 템플릿을 사용할 수 있게 된 **새 프로젝트 추가** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010**  노드.  
  
10. 파일을 저장한 후 닫습니다.  
  
11. **솔루션 탐색기**, 프로젝트 템플릿 또는 항목 템플릿을 프로젝트에 대 한 바로 가기 메뉴를 열고 선택한 후 **프로젝트 다시 로드**합니다.  
  
##### <a name="to-include-a-template-that-you-create-manually"></a>수동으로 만든 서식 파일을 포함 하려면  
  
1.  VSIX 프로젝트에서 서식 파일을 포함 하도록 프로젝트에 새 폴더를 추가 합니다.  
  
2.  이 새 폴더 아래에 다음 하위 폴더를 만들고 서식 파일 (.zip) 파일을 추가 *로캘 ID* 폴더입니다.  
  
     *YourTemplateFolder*  
  
     **SharePoint**  
  
     **SharePoint14**  
  
     *로캘 ID*  
  
     *YourTemplateName*.zip  
  
     예를 들어 영어 (미국) 로캘을 지 원하는 ContosoCustomAction.zip 라는 항목 템플릿을 설정한 경우 전체 경로 ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip 수 있습니다.  
  
3.  **솔루션 탐색기**를 템플릿 파일을 선택 (*YourTemplateName*.zip).  
  
4.  에 **속성** 창에서 설정 된 **빌드 작업** 속성을 **콘텐츠**합니다.  
  
5.  Source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 **열려**합니다.  
  
     파일이는 디자이너에서 열립니다.  
  
6.  에 **자산** 섹션 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
7.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.ItemTemplate** 또는 **Microsoft.VisualStudio.ProjectTemplate**합니다.  
  
8.  에 **소스** 목록에서 선택 **파일 시스템의 파일**합니다.  
  
9. 에 **경로** 필드 어셈블리에 전체 경로 입력 합니다 (예를 들어 **ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip**, 사용 또는 **찾아보기**단추을 찾아 선택 어셈블리를 선택한 후는 **확인** 단추입니다.  
  
##### <a name="to-include-a-wizard-for-a-project-template-or-item-template"></a>프로젝트 템플릿 또는 항목 템플릿에 대 한 마법사를 포함 하려면  
  
1.  VSIX 프로젝트에서 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다.  
  
     파일이는 디자이너에서 열립니다.  
  
2.  에 **자산** 섹션 편집기의 선택은 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.Assembly**합니다.  
  
4.  에 **소스** 목록에서 다음 단계 중 하나를 수행 합니다.  
  
    -   마법사 어셈블리에서 VSIX 프로젝트와 동일한 솔루션에 있는 프로젝트를 빌드할 경우 선택 **현재 솔루션의 프로젝트**합니다. 에 **프로젝트** 목록에서 프로젝트의 이름을 선택 합니다.  
  
    -   마법사 어셈블리를 프로젝트에 파일로 포함할 경우 선택 **파일 시스템의 파일**합니다. 에 **경로** 필드에서 어셈블리 파일의 전체 경로 입력 하거나 사용는 **찾아보기** 단추를 찾아 어셈블리를 선택 합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
### <a name="related-walkthroughs"></a>관련된 연습  
 다음 표에서 다양 한 유형의 SharePoint 도구 확장을 배포 하려면 VSIX 프로젝트를 사용 하는 방법을 보여 주는 연습을 나열 합니다.  
  
|확장 형식|관련된 연습|  
|--------------------|--------------------------|  
|확장 프로그램 어셈블리에만 포함 된 확장|[연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)<br /><br /> [연습: SharePoint 프로젝트 확장명 만들기](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)<br /><br /> [연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)|  
|SharePoint 명령에 포함 된 확장|[연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)<br /><br /> [연습: 서버 탐색기를 확장하여 웹 파트 표시](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
|Visual Studio 템플릿이 포함 된 확장|[연습: 항목 템플릿을 사용하여 사용자 지정 작업 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)|  
|템플릿 마법사가 포함 된 확장|[연습: 항목 템플릿을 사용하여 사용자 지정 작업 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)<br /><br /> [연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 2부](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
  
## <a name="creating-vsix-packages-manually"></a>VSIX 패키지를 수동으로 만들기  
 SharePoint 도구 확장에 대 한 VSIX 패키지를 수동으로 만들려면 하려는 경우 다음 단계를 수행 합니다.  
  
1.  새 폴더에 extension.vsixmanifest 파일 및 [Content_Types].xml 파일을 만듭니다. 자세한 내용은 참조 [VSIX 패키지 분석](/visualstudio/extensibility/anatomy-of-a-vsix-package)합니다.  
  
2.  Windows 탐색기에서 두 개의 XML 파일이 포함 된 폴더를 마우스 오른쪽 단추로 클릭 보내기를 클릭 한 다음 압축 (zip) 폴더를 클릭 합니다. 결과.zip 파일을 Filename은 패키지를 설치 하는 재배포 가능 파일의 이름 Filename.vsix을 바꿉니다.  
  
3.  VSIX 패키지에 확장 어셈블리를 추가 합니다. SharePoint 명령 확장 프로그램의 경우, VSIX 패키지를 SharePoint 명령을 구현 하는 어셈블리를 추가할 수도 있습니다.  
  
4.  Extension.vsixmanifest 파일을 수정 합니다.  
  
    -   추가 `Microsoft.VisualStudio.MefComponent` 요소 아래에서 `Assets` 요소를 제거한 다음 VSIX 패키지에서 확장을 구현 하는 어셈블리의 상대 경로를 새 요소의 값을 설정 합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
    -   SharePoint 명령은 SharePoint에 대 한 서버 개체 모델을 호출 하는 확장 프로그램의 경우, 추가 `Microsoft.VisualStudio.Assembly` 요소 아래에서 `Assets` 요소입니다. VSIX 패키지의 SharePoint 명령을 구현 하는 어셈블리의 상대 경로를 새 요소의 값을 설정 합니다. 자세한 내용은 참조 [자산 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737)합니다.  
  
    -   확장 프로그램 프로젝트 템플릿 또는 항목 템플릿의 포함 하는 경우 추가 `ProjectTemplate` 또는 `ItemTemplate` 요소 아래에서 `Assets` 요소입니다. VSIX 패키지에서 템플릿을 포함 하는 폴더의 상대 경로를 새 요소의 값을 설정 합니다. 자세한 내용은 참조 [ProjectTemplate 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1) 및 [ItemTemplate 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/1d489e54-c1c5-4f96-a510-6c2640867ff0)합니다.  
  
    -   확장 프로그램 프로젝트 템플릿 또는 항목 템플릿에 대 한 사용자 지정 마법사가 포함 된 경우 추가 `Assembly` 요소 아래에서 `Assets` 요소입니다. VSIX 패키지에 어셈블리의 상대 경로를 새 요소의 값을 설정한 다음 설정의 `AssemblyName` 특성을 전체 어셈블리 이름 (버전, culture 및 공개 키 토큰 포함). 자세한 내용은 참조 [Dependency 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/1f63f60a-98ad-48ec-8e44-4eba383d3e37)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 SharePoint 도구 확장에 대 한 extension.vsixmanifest 파일의 내용을 보여 줍니다. 확장은 Contoso.ProjectExtension.dll 라는 어셈블리에서 구현 됩니다. 확장 Contoso.ExtensionCommands.dll 및 명명 된 폴더에서 항목 템플릿을 라고 하는 SharePoint 명령 어셈블리가 포함 **Itemtemplate** VSIX 패키지에 있습니다. 이 예에서는 extension.vsixmanifest 파일 VSIX 패키지에서와 같은 폴더에는 두 어셈블리가 모두 가정 합니다.  
  
```xml 
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">  
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
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)   
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Visual Studio에서 SharePoint 도구에 대한 확장명 디버깅](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  