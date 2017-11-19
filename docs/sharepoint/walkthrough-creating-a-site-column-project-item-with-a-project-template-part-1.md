---
title: "1 부 연습: 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기, | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: b53d48d7-cbf2-45c2-9537-06a6819be397
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1033f33835dfdeefbb4791e356ca50a577b789ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1"></a>연습: 프로젝트 템플릿을 사용하여 사이트 열 프로젝트 항목 만들기, 1부
  SharePoint 프로젝트는 하나 이상의 SharePoint 프로젝트 항목에 대 한 컨테이너입니다. SharePoint 프로젝트 항목 형식을 사용자를 만들고 프로젝트 템플릿을 사용 하 여 연결 하 여 Visual Studio에서 SharePoint 프로젝트 시스템을 확장할 수 있습니다. 이 연습에서는 사이트 열을 만들기 위한 프로젝트 항목 형식을 정의 합니다 및 다음 사이트 열 프로젝트 항목을 포함 하는 새 프로젝트를 만드는 데 사용할 수 있는 프로젝트 템플릿의 만듭니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Visual Studio 확장을 만들 사이트 열에 대 한 SharePoint 프로젝트 항목의 새 형식을 정의 합니다. 프로젝트 항목 형식에 표시 되는 간단한 사용자 지정 속성이 포함 된 **속성** 창.  
  
-   만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 항목에 대 한 서식 파일 프로젝트.  
  
-   작성 한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 프로젝트 템플릿과 확장 어셈블리를 배포 하려면 VSIX (Extension) 패키지 합니다.  
  
-   디버깅 및 프로젝트 항목을 테스트 합니다.  
  
 독립 실행형 연습입니다. 이 연습을 완료 한 후 마법사 프로젝트 템플릿을 추가 하 여 프로젝트 항목을 개선할 수 있습니다. 자세한 내용은 참조 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)합니다.  
  
> [!NOTE]  
>  완료 된 프로젝트, 코드 및이 연습에서는 다음 위치에서 다른 파일을 포함 하는 샘플을 다운로드할 수 있습니다: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 버전의 Microsoft Windows, SharePoint 및 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] 이 연습에서는 **VSIX 프로젝트** 프로젝트 항목을 배포 하려면 VSIX 패키지를 만드는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념에 대 한 지식이 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   Sharepoint에서 사이트 열입니다. 자세한 내용은 참조 [열](http://go.microsoft.com/fwlink/?LinkId=183547)합니다.  
  
-   Visual Studio에서 프로젝트 템플릿입니다. 자세한 내용은 [프로젝트 템플릿 및 항목 템플릿 만들기](/visualstudio/ide/creating-project-and-item-templates)를 참조하세요.  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 세 개의 프로젝트를 만들려면:  
  
-   VSIX 프로젝트입니다. 이 프로젝트는 VSIX 패키지를 사이트 열 프로젝트 항목 및 프로젝트 템플릿 배포를 만듭니다.  
  
-   프로젝트 템플릿 프로젝트입니다. 이 프로젝트에는 사이트 열 프로젝트 항목을 포함 하는 새 SharePoint 프로젝트를 만드는 데 사용할 수 있는 프로젝트 템플릿을 만듭니다.  
  
-   클래스 라이브러리 프로젝트입니다. 사이트 열 프로젝트 항목의 동작을 정의 하는 Visual Studio 확장을 구현 하는이 프로젝트입니다.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  맨 위에 있는 **새 프로젝트** 대화 상자에서 다음 사항을 확인 **.NET Framework 4.5** 버전의.NET Framework의 목록에서 선택 됩니다.  
  
4.  확장은 **Visual Basic** 또는 **Visual C#** 노드를 선택한 후는 **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드를 Visual Studio SDK를 설치 하는 경우에 사용할 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 필수 구성 요소 섹션을 참조 하십시오.  
  
5.  프로젝트 템플릿 목록에서 선택 **VSIX 프로젝트**합니다.  
  
6.  에 **이름** 상자에 입력 **SiteColumnProjectItem**, 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **SiteColumnProjectItem** 프로젝트를 **솔루션 탐색기**합니다.  
  
#### <a name="to-create-the-project-template-project"></a>프로젝트 템플릿 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  맨 위에 있는 **새 프로젝트** 대화 상자에서 다음 사항을 확인 **.NET Framework 4.5** 버전의.NET Framework의 목록에서 선택 됩니다.  
  
3.  확장 된 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **확장성** 노드.  
  
4.  프로젝트 템플릿 목록에서 선택 된 **C# 프로젝트 템플릿을** 또는 **Visual Basic 프로젝트 템플릿을** 템플릿.  
  
5.  에 **이름** 상자에 입력 **SiteColumnProjectTemplate**, 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **SiteColumnProjectTemplate** 프로젝트를 솔루션입니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
7.  Visual Basic 프로젝트를 만든 경우 프로젝트에서 다음 파일 삭제:  
  
    -   MyApplication.Designer.vb  
  
    -   MyApplication.myapp  
  
    -   Resources.Designer.vb  
  
    -   Resources.resx  
  
    -   Settings.Designer.vb  
  
    -   Settings.settings  
  
#### <a name="to-create-the-extension-project"></a>확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  맨 위에 있는 **새 프로젝트** 대화 상자에서 다음 사항을 확인 **.NET Framework 4.5** 버전의.NET Framework의 목록에서 선택 됩니다.  
  
3.  확장은 **Visual C#** 또는 **Visual Basic** 노드를 선택는 **Windows** 노드를 선택한 후는 **클래스 라이브러리** 서식 파일입니다.  
  
4.  에 **이름** 상자에 입력 **ProjectItemTypeDefinition** 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]추가 **ProjectItemTypeDefinition** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-extension-project"></a>확장 프로젝트 구성  
 코드 파일 및 확장 프로젝트를 구성 하는 어셈블리 참조를 추가 합니다.  
  
#### <a name="to-configure-the-project"></a>프로젝트를 구성 하려면  
  
1.  ProjectItemTypeDefinition 프로젝트에서 명명 된 코드 파일을 추가 **SiteColumnProjectItemTypeProvider**합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
3.  에 **참조 관리자-ProjectItemTypeDefinition** 대화 상자에서 **어셈블리** 노드를 선택는 **프레임 워크** 노드를 선택한 후는 System.ComponentModel.Composition 확인란입니다.  
  
4.  선택 된 **확장** 노드를 Microsoft.VisualStudio.SharePoint 어셈블리 옆의 확인란을 선택한 다음 선택는 **확인** 단추입니다.  
  
## <a name="defining-the-new-sharepoint-project-item-type"></a>새 SharePoint 프로젝트 항목 형식 정의  
 구현 하는 클래스를 만들기는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 새 프로젝트 항목 종류의 동작을 정의 하는 인터페이스입니다. 새로운 형식의 프로젝트 항목을 정의 하려는 경우이 인터페이스를 구현 합니다.  
  
#### <a name="to-define-the-new-sharepoint-project-item-type"></a>새 SharePoint 프로젝트 항목 형식 정의 하려면  
  
1.  에 **SiteColumnProjectItemTypeProvider** 코드 파일 기본 코드를 다음 코드로 바꾼 다음 파일을 저장 합니다.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.vb#1)]  
  
## <a name="creating-a-visual-studio-project-template"></a>Visual Studio 프로젝트 템플릿 만들기  
 프로젝트 템플릿을 만들면 하면 다른 개발자가 사이트 열 프로젝트 항목을 포함 하는 SharePoint 프로젝트를 만들 수 있습니다. SharePoint 프로젝트 템플릿을.csproj 또는.vbproj 및.vstemplate 파일을 SharePoint 프로젝트에만 적용 되는 파일 등 Visual Studio에서 모든 프로젝트에 대해 필요한 파일을 포함 합니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
 이 절차에서는 SharePoint 프로젝트에 관련 된 파일을 생성 하는 빈 SharePoint 프로젝트를 만듭니다. 그런 다음 이러한 파일에 추가한 SiteColumnProjectTemplate 프로젝트는이 프로젝트에서 생성 되는 서식 파일에 포함 하는 합니다. 구성할 수도 SiteColumnProjectTemplate 프로젝트 파일에서 해당 프로젝트 템플릿이 표시 되는 위치를 지정 하는 **새 프로젝트** 대화 상자.  
  
#### <a name="to-create-the-files-for-the-project-template"></a>프로젝트 템플릿에 대 한 파일을 만들려면  
  
1.  두 번째 인스턴스를 시작 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 관리 자격 증명을 사용 합니다.  
  
2.  명명 된 SharePoint 2010 프로젝트를 만들 **BaseSharePointProject**합니다.  
  
    > [!IMPORTANT]  
    >  에 **SharePoint 사용자 지정 마법사**, 선택 하지 않은 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
3.  프로젝트에 빈 요소 항목을 추가 하 고 다음 항목의 이름을 **Field1**합니다.  
  
4.  프로젝트를 저장 한 다음의 두 번째 인스턴스를 닫습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
5.  인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SiteColumnProjectItem 솔루션 열기를에 올려진 **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SiteColumnProjectTemplate** 프로젝트 노드를 선택 **추가**를 선택한 후 **기존 항목**합니다.  
  
6.  에 **기존 항목 추가** 대화 상자에서 파일 확장명의 목록 상자를 열고 다음 선택 **모든 파일 (\*.\*)** .  
  
7.  BaseSharePointProject 프로젝트가 포함 된 디렉터리에 key.snk 파일을 선택한 다음 선택에서 **추가** 단추입니다.  
  
    > [!NOTE]  
    >  이 연습에서는 프로젝트 템플릿을 만드는 템플릿을 사용 하 여 만들어진 각 프로젝트를 서명 하 동일한 key.snk 파일을 사용 합니다. 각 프로젝트 인스턴스에 대 한 다른 key.snk 파일을 만들려면이 샘플을 확장 하는 방법을 알아보려면 참조 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)합니다.  
  
8.  BaseSharePointProject 디렉터리에서 지정 된 하위 폴더에서 다음 파일을 추가 하려면 5-8 단계를 반복 합니다.  
  
    -   \Field1\Elements.xml  
  
    -   \Field1\SharePointProjectItem.spdata  
  
    -   \Features\Feature1\Feature1.feature  
  
    -   \Features\Feature1\Feature1.Template.xml  
  
    -   \Package\Package.package  
  
    -   \Package\Package.Template.xml  
  
     이러한 파일 SiteColumnProjectTemplate 프로젝트;에 직접 추가 안 함 Field1, 기능 또는 패키지 하위 폴더를에 있는 프로젝트를 다시 만듭니다. 이러한 파일에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
#### <a name="to-configure-how-developers-discover-the-project-template-in-the-new-project-dialog-box"></a>개발자가 새 프로젝트 대화 상자에서 프로젝트 템플릿을 검색 하는 방법을 구성 하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SiteColumnProjectTemplate** 프로젝트 노드를 선택한 후 **프로젝트 언로드**합니다. 모든 파일 변경 내용을 저장 하는 메시지가 선택 된 **예** 단추입니다.  
  
2.  에 대 한 바로 가기 메뉴를 열고는 **SiteColumnProjectTemplate** 노드를 다시 마우스 선택 **편집 SiteColumnProjectTemplate.csproj** 또는 **편집 SiteColumnProjectTemplate.vbproj**.  
  
3.  프로젝트 파일에서 다음을 찾아 `VSTemplate` 요소입니다.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
    ```  
  
4.  이 요소를 다음 XML로 바꿉니다.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` 요소 프로젝트를 빌드할 때 프로젝트 템플릿이 생성 되었는지 경로에 추가 폴더를 지정 합니다. 여기에 지정 된 폴더는 고객 열면 프로젝트 템플릿을 사용할 수 있게 된 **새 프로젝트** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010**  노드.  
  
5.  파일을 저장한 후 닫습니다.  
  
6.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SiteColumnProjectTemplate** 프로젝트를 선택한 후 **프로젝트 다시 로드**합니다.  
  
## <a name="editing-the-project-template-files"></a>프로젝트 템플릿 파일 편집  
 SiteColumnProjectTemplate 프로젝트의 프로젝트 템플릿의 동작을 정의 하는 다음 파일을 편집 합니다.  
  
-   AssemblyInfo.cs 또는 AssemblyInfo.vb  
  
-   Elements.xml  
  
-   SharePointProjectItem.spdata  
  
-   Feature1.feature  
  
-   있습니다. 패키지  
  
-   SiteColumnProjectTemplate.vstemplate  
  
-   ProjectTemplate.csproj 또는 ProjectTemplate.vbproj  
  
 다음 절차에서 이러한 파일 중 일부에 대 한 대체 가능 매개 변수를 추가 합니다. 대체 가능 매개 변수는 시작 하 고 달러 기호 ($) 문자로 끝나는 토큰입니다. 프로젝트를 만들려면이 프로젝트 템플릿을 사용 하는 사용자를 하는 경우 Visual Studio 새 프로젝트에서 이러한 매개 변수 특정 값으로 자동 대체 됩니다. 자세한 내용은 참조 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)합니다.  
  
#### <a name="to-edit-the-assemblyinfocs-or-assemblyinfovb-file"></a>AssemblyInfo.cs 또는 AssemblyInfo.vb 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트의 AssemblyInfo.cs 또는 AssemblyInfo.vb 파일 열고의 맨 위에 다음 문을 추가 합니다.  
  
    ```vb  
    Imports System.Security  
    ```  
  
    ```csharp  
    using System.Security;  
    ```  
  
     때는 **샌드박스 솔루션** SharePoint 프로젝트의 속성이로 설정 되어 **True**, 추가 하는 Visual Studio는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> AssemblyInfo 코드 파일에 있습니다. 그러나 서식 파일 프로젝트의에서 AssemblyInfo 코드 파일을 가져올 하지 않습니다는 <xref:System.Security> 기본적으로 네임 스페이스입니다. 이 추가 해야 **를 사용 하 여** 또는 **Imports** 문을 방지 하기 위해 컴파일 오류입니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-elementsxml-file"></a>Elements.xml 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Elements.xml 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
          Name="$safeprojectname$"   
          DisplayName="$projectname$"   
          Type="Text"   
          Group="Custom Columns">  
      </Field>  
    </Elements>  
    ```  
  
     새 XML 추가 `Field` 사이트 열, 기본 형식 및 갤러리에 사이트 열을 나열 하는 그룹의 이름을 정의 하는 요소입니다. 이 파일의 내용에 대 한 자세한 내용은 참조 [필드 정의 스키마](http://go.microsoft.com/fwlink/?LinkId=184290)합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-sharepointprojectitemspdata-file"></a>SharePointProjectItem.spdata 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 SharePointProjectItem.spdata 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ProjectItem Type="Contoso.SiteColumn" DefaultFile="Elements.xml"   
                 xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$safeprojectname$\" Type="ElementManifest" />  
      </Files>   
    </ProjectItem>  
    ```  
  
     새 XML 파일을 변경한 다음:  
  
    -   변경은 `Type` 특성의는 `ProjectItem` 요소에 전달 되는 동일한 문자열에는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> 프로젝트 항목 정의에서 (는 `SiteColumnProjectItemTypeProvider` 이 연습의 앞부분에서 만든 클래스).  
  
    -   제거는 `SupportedTrustLevels` 및 `SupportedDeploymentScopes` 에서 특성은 `ProjectItem` 요소입니다. 신뢰 수준 및 배포 범위에 지정 된 특성 값이 필요 하지 않습니다는 `SiteColumnProjectItemTypeProvider` ProjectItemTypeDefinition 프로젝트의 클래스.  
  
     .Spdata 파일의 내용에 대 한 자세한 내용은 참조 하십시오. [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-feature1feature-file"></a>Feature1.feature 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Feature1.feature 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <feature xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="$guid4$" featureId="$guid4$"   
             imageUrl="" solutionId="00000000-0000-0000-0000-000000000000" title="Site Column Feature1" version=""  
             deploymentPath="$SharePoint.Project.FileNameWithoutExtension$_$SharePoint.Feature.FileNameWithoutExtension$"  
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/FeatureModel">  
      <projectItems>  
        <projectItemReference itemId="$guid2$" />  
      </projectItems>  
    </feature>  
    ```  
  
     새 XML 파일을 변경한 다음:  
  
    -   값을 변경는 `Id` 및 `featureId` 의 특성은 `feature` 요소를 `$guid4$`합니다.  
  
    -   값을 변경는 `itemId` 특성에는 `projectItemReference` 요소의 `$guid2$`합니다.  
  
     .Feature 파일에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-packagepackage-file"></a>있습니다. 패키지 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 Package.package 파일의 내용을 다음 XML로 대체 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <package xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0"   
             Id="$guid3$" solutionId="$guid3$" resetWebServer="false" name="$safeprojectname$"   
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/PackageModel">  
      <features>  
        <featureReference itemId="$guid4$" />  
      </features>  
    </package>  
    ```  
  
     새 XML 파일을 변경한 다음:  
  
    -   값을 변경는 `Id` 및 `solutionId` 의 특성은 `package` 요소를 `$guid3$`합니다.  
  
    -   값을 변경는 `itemId` 특성에는 `featureReference` 요소의 `$guid4$`합니다.  
  
     .Package 파일에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-sitecolumnprojecttemplatevstemplate-file"></a>SiteColumnProjectTemplate.vstemplate 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 XML의 다음 섹션 중 하 나와 SiteColumnProjectTemplate.vstemplate 파일의 내용을 바꿉니다.  
  
    -   Visual C# 프로젝트 템플릿을 만드는 경우 다음과 같은 XML을 사용 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
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
  
    -   Visual Basic 프로젝트 템플릿을 만드는 경우 다음과 같은 XML을 사용 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
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
  
     새 XML 파일을 변경한 다음:  
  
    -   설정의 `Name` 값 **사이트 열**합니다. (이 이름은에 표시 된 **새 프로젝트** 대화 상자).  
  
    -   추가 `ProjectItem` 각 filethat에 대 한 요소의 인스턴스마다 프로젝트에에서 포함 합니다.  
  
    -   "Http://schemas.microsoft.com/developer/vstemplate/2005" 네임 스페이스를 사용 합니다. 이 솔루션의 다른 프로젝트 파일 http://schemas.microsoft.com/developer/msbuild/2003 네임 스페이스를 사용 합니다. 따라서 XML 스키마 경고 메시지가 생성 될 있지만이 연습에서 무시할 수 있습니다.  
  
     .Vstemplate 파일의 내용에 대 한 자세한 내용은 참조 하십시오. [Visual Studio 템플릿 스키마 참조](/visualstudio/extensibility/visual-studio-template-schema-reference)합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
#### <a name="to-edit-the-projecttemplatecsproj-or-projecttemplatevbproj-file"></a>ProjectTemplate.csproj 또는 ProjectTemplate.vbproj 파일을 편집 하려면  
  
1.  SiteColumnProjectTemplate 프로젝트에서 XML의 다음 섹션 중 하 나와 ProjectTemplate.csproj 파일이 나 ProjectTemplate.vbproj 파일의 내용을 바꿉니다.  
  
    -   Visual C# 프로젝트 템플릿을 만드는 경우 다음과 같은 XML을 사용 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
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
  
    1.  Visual Basic 프로젝트 템플릿을 만드는 경우 다음과 같은 XML을 사용 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
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
  
     새 XML 파일을 변경한 다음:  
  
    -   사용 하 여는 `TargetFrameworkVersion` 하지 4.5.NET Framework 3.5를 지정 하는 요소입니다.  
  
    -   추가 `SignAssembly` 및 `AssemblyOriginatorKeyFile` 요소를 사용 하 여 프로젝트 출력에 서명 합니다.  
  
    -   추가 `Reference` 어셈블리에 대 한 요소를 사용 하는 SharePoint 프로젝트 참조 합니다.  
  
    -   Elements.xml 및 SharePointProjectItem.spdata 같은 프로젝트의 각 기본 파일에 대 한 요소를 추가합니다.  
  
2.  파일을 저장한 후 닫습니다.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-template"></a>VSIX 패키지 프로젝트 템플릿을 배포를 만들기  
 VSIX 프로젝트를 사용 하 여 확장을 배포 하는 **SiteColumnProjectItem** 솔루션 VSIX 패키지를 만듭니다. 첫째, VSIX 프로젝트에 포함 된 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다. 그런 다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>구성 하 고 VSIX 패키지를 만들려면  
  
1.  **솔루션 탐색기**에 **SiteColumnProjectItem** 프로젝트에서 매니페스트 편집기에서 source.extension.vsixmanifest 파일을 엽니다.  
  
     Source.extension.vsixmanifest 파일은 필요한 모든 VSIX 패키지 extension.vsixmanifest 파일의 기준이 됩니다. 이 파일에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다.  
  
2.  에 **제품 이름** 상자에 입력 **사이트 열**합니다.  
  
3.  에 **작성자** 상자에 입력 **Contoso**합니다.  
  
4.  에 **설명** 상자에 입력 **사이트 열을 만들기 위한 SharePoint 프로젝트**합니다.  
  
5.  선택 된 **자산** 탭을 선택 합니다는 **새로** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
6.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.ProjectTemplate**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `ProjectTemplate` extension.vsixmanifest 파일의 요소입니다. 이 요소는 프로젝트 템플릿이 포함 된 VSIX 패키지의 하위 폴더를 식별 합니다. 자세한 내용은 참조 [ProjectTemplate 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1)합니다.  
  
7.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
8.  에 **프로젝트** , 목록을 열고 **SiteColumnProjectTemplate**, 선택한 후는 **확인** 단추입니다.  
  
9. 선택 된 **새로** 단추를 다시 합니다.  
  
     **새 자산 추가** 대화 상자가 열립니다.  
  
10. 에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `MefComponent` extension.vsixmanifest 파일의 요소입니다. 이 요소는 VSIX 패키지의 확장 어셈블리의 이름을 지정합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
11. 에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
12. 에 **프로젝트** 목록에서 선택 **ProjectItemTypeDefinition**를 선택한 후는 **확인** 단추입니다.  
  
13. 메뉴 모음에서 **빌드**, **솔루션 빌드**, 프로젝트가 오류 없이 컴파일되는지 확인 합니다.  
  
## <a name="testing-the-project-template"></a>프로젝트 템플릿 테스트  
 이제 테스트 프로젝트 템플릿을 준비가 되었습니다. 먼저 Visual Studio의 실험적 인스턴스에서 SiteColumnProjectItem 솔루션 디버깅을 시작 합니다. 그런 다음 테스트는 **사이트 열** Visual Studio의 실험적 인스턴스에서 프로젝트. 마지막으로, 빌드 및 사이트 열이 예상 대로 작동 하는지 확인 하기 위해 SharePoint 프로젝트를 실행 합니다.  
  
#### <a name="to-start-debugging-the-solution"></a>솔루션 디버깅을 시작 하려면  
  
1.  관리 자격 증명으로 Visual Studio를 다시 시작 하 고 SiteColumnProjectItem 솔루션을 엽니다.  
  
2.  
  
3.  SiteColumnProjectItemTypeProvider 코드 파일에서 중단점에 코드의 첫 번째 줄을 추가 `InitializeType` 메서드를 선택한 후는 **F5** 키 디버깅을 시작 합니다.  
  
     Visual Studio에서는 %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\Site Column\1.0에 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-project-in-visual-studio"></a>Visual Studio에서 프로젝트를 테스트 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **파일**, **새로**, **프로젝트**합니다.  
  
2.  확장는 **Visual C#** 또는 **Visual Basic** 노드 (언어에 따라 프로젝트 템플릿은 지원)를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
3.  프로젝트 템플릿 목록에서 선택 된 **사이트 열** 템플릿.  
  
4.  에 **이름** 상자에 입력 **SiteColumnTest** 선택한 후는 **확인** 단추입니다.  
  
     **솔루션 탐색기**, 라는 프로젝트 항목과 새 프로젝트가 표시 **Field1**합니다.  
  
5.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `InitializeType` 메서드를 선택한 후는 **F5** 프로젝트 디버깅을 계속 하려면는 키입니다.  
  
6.  **솔루션 탐색기**, 선택는 **Field1** 노드를 선택한 후는 **F4** 키입니다.  
  
     **속성** 창이 열립니다.  
  
7.  속성 목록 확인 속성 **예제 속성** 나타납니다.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>Sharepoint에서 사이트 열을 테스트 하려면  
  
1.  **솔루션 탐색기**, 선택는 **SiteColumnTest** 노드.  
  
2.  에 **속성** 창 옆에 있는 텍스트 상자에는 **사이트 URL** 속성, 입력 **http://localhost**합니다.  
  
     이 단계는 디버깅에 사용할 개발 컴퓨터에서 로컬 SharePoint 사이트를 지정 합니다.  
  
    > [!NOTE]  
    >  **사이트 URL** 속성은 기본적으로 비어 있으므로 사이트 열 프로젝트 템플릿에 프로젝트를 만들 때이 값을 수집 하기 위한 마법사를 제공 하지 않습니다. 이 값에 대 한 개발자 문의 한 후 새 프로젝트에서이 속성을 구성 하는 마법사를 추가 하는 방법을 알아보려면 참조 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)합니다.  
  
3.  선택 된 **F5** 키입니다.  
  
     사이트 열 포장,에 지정 된 SharePoint 사이트에 배포 되는 **사이트 URL** 프로젝트의 속성입니다. 이 사이트의 기본 페이지에는 웹 브라우저를 엽니다.  
  
    > [!NOTE]  
    >  경우는 **스크립트 디버깅 사용 안 함** 선택 대화 상자가 나타나면는 **예** 프로젝트 디버깅을 계속 하려면는 단추입니다.  
  
4.  에 **사이트 작업** 메뉴 선택 **사이트 설정**합니다.  
  
5.  에 **사이트 설정** 페이지의 **갤러리** 목록에서 선택 된 **열 사이트** 링크 합니다.  
  
6.  사이트 열 목록에 있는지를 확인 한 **사용자 지정 열** 그룹 이라는 열이 포함 되어 **SiteColumnTest**합니다.  
  
7.  웹 브라우저를 닫습니다.  
  
## <a name="cleaning-up-the-development-computer"></a>개발 컴퓨터를 정리합니다.  
 프로젝트 테스트를 마친 후 프로젝트 템플릿을 Visual Studio의 실험적 인스턴스에서 제거 합니다.  
  
#### <a name="to-clean-up-the-development-computer"></a>개발 컴퓨터를 정리 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택는 **사이트 열** 확장을 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택 된 **예** 확장을 제거 하려면 확인 단추입니다.  
  
4.  선택 된 **닫기** 단추 제거를 완료 합니다.  
  
5.  Visual Studio (실험적 인스턴스 및 SiteColumnProjectItem 솔루션 열릴 Visual Studio의 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습을 완료 한 후에 프로젝트 템플릿에 마법사를 추가할 수 있습니다. 사용자가 사이트 열 프로젝트를 만들 때 마법사는 사이트에 사용할 URL 디버깅 및 새 솔루션에 샌드박스가 적용 되는지 여부에 대 한 사용자에 게 요청 하 고 마법사가이 정보로 새 프로젝트를 구성 합니다. 또한 마법사는 열 (예: 기본 형식 및 사이트 열 갤러리에 있는 열을 나열 하는 그룹)에 대 한 정보를 수집 하 고 새 프로젝트에서 Elements.xml 파일에이 정보를 추가 합니다. 자세한 내용은 참조 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 2 부 프로젝트 템플릿을 사용 하 여 사이트 열 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [SharePoint 프로젝트 시스템의 확장에 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [SharePoint 도구 확장과 사용자 지정 데이터 연결](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  