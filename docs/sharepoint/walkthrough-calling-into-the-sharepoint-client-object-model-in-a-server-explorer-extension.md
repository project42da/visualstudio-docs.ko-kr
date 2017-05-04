---
title: "Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension | Microsoft Docs"
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
  - "SharePoint development in Visual Studio, client object model"
  - "SharePoint commands [SharePoint development in Visual Studio]"
ms.assetid: 897d3798-42c1-4fff-b280-8b84b53d80c6
caps.latest.revision: 100
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 96
---
# Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension
  이 연습에서는 **서버 탐색기**의 **SharePoint 연결** 노드용 확장에서 SharePoint 클라이언트 개체 모델을 호출하는 방법을 보여 줍니다.  SharePoint 클라이언트 개체 모델을 사용 하는 방법에 대 한 자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   다음과 같은 방법으로 **서버 탐색기**의 **SharePoint 연결** 노드를 확장하는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장 만들기  
  
    -   확장명 추가 된  **웹 파트 갤러리** 노드 아래에서 각 SharePoint 사이트 노드의  **서버 탐색기**.  새 노드에는 사이트에서 웹 파트 갤러리의 각 웹 파트를 나타내는 자식 노드가 포함됩니다.  
  
    -   확장 웹 파트 인스턴스를 나타내는 노드의 새 형식을 정의 합니다.  새 노드 형식은 새 **웹 파트 갤러리** 노드 아래에 있는 자식 노드의 기반이 됩니다.  에 정보를 표시 하는 새 웹 파트 노드 형식이 있는  **속성** 노드를 나타내는 웹 파트에 대 한 창.  
  
-   확장을 배포하기 위한 VSIX\(Visual Studio Extension\) 패키지 빌드  
  
-   확장 디버깅 및 테스트  
  
> [!NOTE]  
>  이 연습에서 만드는 확장에서 만드는 확장과 비슷합니다 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  이 연습에서는 SharePoint 서버 개체 모델을 사용 하지만이 연습에서는 클라이언트 개체 모델을 사용 하 여 동일한 작업을 수행.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전의 Windows, SharePoint 및 Visual Studio.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio SDK입니다.  이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 확장을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   SharePoint 클라이언트 개체 모델 사용.  자세한 내용은 [Managed Client Object Model](http://go.microsoft.com/fwlink/?LinkId=177797)을 참조하십시오.  
  
-   Sharepoint에서 웹 파트입니다.  자세한 내용은 [Web Parts Overview](http://go.microsoft.com/fwlink/?LinkId=177803)를 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료하려면 두 프로젝트를 만들어야 합니다.  
  
-   VSIX 패키지를 만들어 **서버 탐색기** 확장을 배포하기 위한 VSIX 프로젝트입니다.  
  
-   **서버 탐색기** 확장을 구현하는 클래스 라이브러리 프로젝트입니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  에  **새 프로젝트** 대화 상자에서 확장 된  **C\#** 또는  **Visual Basic** 노드를 다음 선택  **확장성**.  
  
    > [!NOTE]  
    >  **확장성** 노드인 Visual Studio SDK를 설치한 경우에 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
4.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
     SharePoint 도구 확장 기능은이 버전의.NET Framework 해야합니다.  
  
5.  선택 된  **VSIX 프로젝트** 템플릿.  
  
6.  에  **이름** 상자에 입력  **WebPartNode**, 다음 선택은  **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **WebPartNode** 프로젝트를 추가합니다.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, 솔루션 노드 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장 된  **C\#** 또는  **Visual Basic** 노드를 다음 선택  **Windows**.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
4.  프로젝트 템플릿 목록에서 선택  **클래스 라이브러리**.  
  
5.  에  **이름** 상자에 입력  **WebPartNodeExtension**, 다음 선택은  **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **WebPartNodeExtension** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 확장 프로젝트 구성  
 확장을 만드는 코드를 작성 하기 전에 코드 파일과 어셈블리 참조를 프로젝트에 추가 해야 하며 기본 네임 스페이스를 업데이트 해야 합니다.  
  
#### 프로젝트를 구성하려면  
  
1.  에  **WebPartNodeExtension** 프로젝트, SiteNodeExtension 및 WebPartNodeTypeProvider 라는 두 개의 코드 파일을 추가 합니다.  
  
2.  WebPartNodeExtension 프로젝트에 대 한 바로 가기 메뉴를 열고 선택  **참조 추가**.  
  
3.  에  **참조 관리자 – WebPartNodeExtension** 대화 상자에서 선택 된  **프레임 워크** 노드를 선택한 다음 선택 확인란 System.ComponentModel.Composition 및 System.Windows.Forms 어셈블리에 대 한.  
  
4.  선택은  **확장** 노드를 각각 다음 어셈블리에 대 한 확인란을 선택 하 고 선택은  **확인** 단추:  
  
    -   Microsoft.SharePoint.Client  
  
    -   Microsoft.SharePoint.Client.Runtime  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  바로 가기 메뉴를 열고를  **WebPartNodeExtension** 프로젝트를 하 고 선택  **속성**.  
  
     **프로젝트 디자이너**가 열립니다.  
  
6.  선택 된  **응용 프로그램** 탭입니다.  
  
7.  에 있는  **기본 네임 스페이스** 상자 \(C\#\) 또는  **루트 네임 스페이스** \(Visual Basic\) 상자에 입력  **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## 새 노드의 아이콘 만들기  
 두 개의 아이콘을 만들는  **서버 탐색기** 확장: 아이콘에 새  **웹 파트 갤러리** 노드와 각 자식 웹 파트 노드 아래에 대 한 다른 아이콘은  **웹 파트 갤러리** 노드.  이 연습의 뒷부분에서 이러한 아이콘을 노드에 연결 하는 코드를 작성 합니다.  
  
#### 노드의 아이콘을 만들려면  
  
1.  에  **프로젝트 디자이너** WebPartNodeExtension 프로젝트에 대 한 선택은  **리소스** 탭.  
  
2.  링크 선택  **이 프로젝트에는 기본 리소스 파일이 없습니다. 기본 리소스 파일을 만들려면 여기를 클릭하십시오.**를 클릭합니다.  
  
     Visual Studio 리소스 파일을 만들고 디자이너에서 열립니다.  
  
3.  디자이너의 위쪽에 있는 화살표를 선택한는  **리소스 추가** 메뉴에서 명령을 클릭 한 다음 선택  **새 아이콘 추가**.  
  
4.  입력  **WebPartsNode** 새 아이콘에 대 한 이름을 지정 하 고 다음 선택은  **추가** 단추.  
  
     새 아이콘이 **이미지 편집기**에서 열립니다.  
  
5.  디자인을 쉽게 인식할 수 있도록 16x16 버전의 아이콘 편집 합니다.  
  
6.  32X32 버전의 아이콘, 바로 가기 메뉴를 열고 선택  **이미지 형식 삭제**.  
  
7.  3 단계에서 두 번째 아이콘은 프로젝트 리소스에 추가 하려면 7 단계를 반복 하 고이 아이콘 이름을  **WebPart**.  
  
8.  **솔루션 탐색기**에서  **리소스** 폴더에는  **WebPartNodeExtension** 프로젝트를 선택  **WebPartsNode.ico**.  
  
9. 에  **속성** 창이 열리고는  **빌드 작업** 선택한 다음 선택  **포함 리소스**.  
  
10. **WebPart.ico**에 대해 마지막 두 단계를 반복합니다.  
  
## 서버 탐색기에 웹 파트 갤러리 노드 추가  
 각 SharePoint 사이트 노드에 새 **웹 파트 갤러리** 노드를 추가하는 클래스를 만듭니다.  새 코드를 추가하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현합니다.  노드에 새 자식 노드 추가 등 **서버 탐색기**에서 기존 노드의 동작을 확장하려는 경우 이 인터페이스를 구현합니다.  
  
#### 서버 탐색기에 웹 파트 갤러리 노드를 추가하려면  
  
1.  다음 코드를 붙여 넣습니다는  **SiteNodeExtension** 코드 파일에는  **WebPartNodeExtension** 프로젝트입니다.  
  
    > [!NOTE]  
    >  이 코드를 추가한 후 프로젝트에 컴파일 오류가 발생 해야 합니다.  이러한 오류는 이후 단계에서 코드를 추가하면 사라집니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnode/cs/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnode/vb/webpartnodeextension/sitenodeextension.vb#1)]  
  
## 웹 파트를 나타내는 노드 형식 정의  
 웹 파트를 나타내는 새 노드 형식을 정의하는 클래스를 만듭니다.  Visual Studio 새 노드 형식을 사용 하 여 아래에서 자식 노드를 표시 하는  **웹 파트 갤러리** 노드.  이러한 각 자식 노드는 SharePoint 사이트에서 하나의 웹 파트를 나타냅니다.  
  
 새 노드 형식을 정의하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스를 구현합니다.  **서버 탐색기**에서 새 노드 형식을 정의하려는 경우 이 인터페이스를 구현합니다.  
  
#### 웹 파트 노드 형식을 정의하려면  
  
1.  다음 코드를 붙여 넣습니다는  **WebPartNodeTypeProvider** 코드 파일에는  **WebPartNodeExtension** 프로젝트입니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnode/cs/webpartnodeextension/webpartnodetypeprovider.cs#2)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnode/vb/webpartnodeextension/webpartnodetypeprovider.vb#2)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 **웹 파트 갤러리** 노드를 위한 모든 코드가 프로젝트에 포함되었습니다.  빌드는  **WebPartNodeExtension** 프로젝트를 오류 없이 컴파일되는지 확인 합니다.  
  
#### 프로젝트를 빌드하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는  **WebPartNodeExtension** 프로젝트를 하 고 선택  **빌드**.  
  
## 확장을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  먼저, 프로젝트에 포함 되어 있는 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다.  다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하려면  
  
1.  **솔루션 탐색기**에서  **WebPartNode** 열린 프로젝트  **source.extension.vsixmanifest** 파일이 매니페스트 편집기에서.  
  
     Source.extension.vsixmanifest 파일이 모든 VSIX 패키지를 요구 하는 extension.vsixmanifest 파일에 대 한 기반이 됩니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  에 있는  **제품명** 상자에 입력  **서버 탐색기에 웹 파트 갤러리 노드**.  
  
3.  에 있는  **작성자** 상자에 입력  **Contoso**.  
  
4.  에 있는  **설명** 상자에 입력  **에 서버 탐색기에서의 SharePoint 연결 노드에 사용자 지정 웹 파트 갤러리 노드 추가**.  
  
5.  에  **자산** 탭 편집기의 선택은  **New** 단추.  
  
6.  에  **추가 새 자산** 대화 상자에  **유형** 목록에서 선택  **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
7.  에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
8.  에  **프로젝트** 목록에서 선택  **WebPartNodeExtension**, 다음 선택은  **확인** 단추입니다.  
  
9. 메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**, 및 다음 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
10. WebPartNode 프로젝트의 빌드 출력 폴더에 이제 WebPartNode.vsix 파일이 들어 있는지 확인 합니다.  
  
     기본적으로 빌드 출력 경로는 프로젝트 파일이 포함된 폴더 아래에 있는 ..  \\bin\\Debug 폴더입니다.  
  
## 확장 테스트  
 이제 **서버 갤러리**에서 새 **웹 파트 갤러리** 노드를 테스트할 준비가 되었습니다.  Visual Studio 실험적 인스턴스에서 확장 프로젝트를 디버깅 하려면 먼저 시작 합니다.  새를 사용  **웹 파트** Visual Studio 실험적 인스턴스에서 노드.  
  
#### 확장 디버깅을 시작하려면  
  
1.  Visual Studio 관리자 자격 증명으로 다시 시작 하 고 다음 열에서  **WebPartNode** 솔루션입니다.  
  
2.  WebPartNodeExtension 프로젝트를 엽니다의  **SiteNodeExtension** 파일, 코드 및 중단점을 추가 하는 코드 첫 줄에는 `NodeChildrenRequested` 및 `CreateWebPartNodes` 메서드.  
  
3.  F5 키를 선택하여 디버깅을 시작합니다.  
  
     Visual Studio 서버 explorer\\1.0에 대해 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0Exp\\Extensions\\Contoso\\Web 파트 갤러리 노드를 확장 하 여 확장을 설치 하 고 Visual Studio 실험 인스턴스를 시작 합니다.  프로젝트 항목에 Visual Studio이 인스턴스를 테스트 합니다.  
  
#### 확장을 테스트하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **보기**,  **서버 탐색기**.  
  
2.  테스트에 사용할 SharePoint 사이트가 **서버 탐색기**의 **SharePoint 연결** 노드 아래에 표시되는지 확인합니다.  나열 되어 있지 않으면 다음과 같이 하십시오.  
  
    1.  바로 가기 메뉴를 열고  **SharePoint 연결**, 다음 선택  **연결 추가**.  
  
    2.  에 있는  **SharePoint 연결 추가** 대화 상자에서 적용할 연결, 및 다음 선택 하려면 SharePoint 사이트에 대 한 URL을 입력의  **확인** 단추.  
  
         개발 컴퓨터의 SharePoint 사이트를 지정하려면 **http:\/\/localhost**를 입력합니다.  
  
3.  사이트의 URL을 표시 하 고 사이트 연결 노드를 확장 한 다음 자식 사이트 노드를 확장 합니다 \(예를 들어,  **팀 사이트**\).  
  
4.  코드 Visual Studio 인스턴스를 이전에 설정한 중단점에서 중지 하는지 확인은 `NodeChildrenRequested` 메서드를 다음 프로젝트에 디버깅을 계속 하려면 F5 키를 선택 합니다.  
  
5.  Visual Studio 실험적 인스턴스에서 확장을  **웹 파트 갤러리** 노드가 최상위 사이트 노드 아래에 나타납니다.  
  
6.  코드 Visual Studio 인스턴스를 이전에 설정한 중단점에서 중지 하는지 확인은 `CreateWebPartNodes` 메서드를 다음 프로젝트에 디버깅을 계속 하려면 F5 키를 선택 합니다.  
  
7.  실험 모드의 Visual Studio 인스턴스에서 연결된 사이트의 모든 웹 파트가 **서버 탐색기**의 **웹 파트 갤러리** 노드 아래에 표시되는지 확인합니다.  
  
8.  웹 파트에 대 한 바로 가기 메뉴를 열고 선택  **속성이**.  
  
9. 에  **속성** 창에서 웹 파트에 대 한 세부 정보가 표시 되는지 확인 하십시오.  
  
10. **서버 탐색기**, 바로 가기 메뉴에서 동일한 웹 파트를 열고 선택  **메시지 표시**.  
  
     나타나는 메시지 상자에서 선택 된  **확인** 단추입니다.  
  
## Visual Studio에서 확장 제거  
 확장 테스트를 마친 후 Visual Studio 제거 합니다.  
  
#### 확장을 제거하려면  
  
1.  Visual Studio 실험적 인스턴스에서 메뉴 표시줄에서 선택  **도구**,  **확장 및 업데이트**.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장명 목록에서 선택한  **서버 탐색기에 웹 파트 갤러리 노드**, 다음 선택은  **제거** 단추입니다.  
  
3.  나타나는 대화 상자에서 선택 된  **예** 단추입니다.  
  
4.  선택은  **이제 다시** 단추 제거를 완료 합니다.  
  
     프로젝트 항목도 제거됩니다.  
  
5.  Visual Studio \(Visual Studio WebPartNode 솔루션에 열려 있는 인스턴스 및 실험적 인스턴스\)을 모두 닫습니다.  
  
## 참고 항목  
 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Image Editor for Icons](/visual-cpp/windows/image-editor-for-icons)   
 [Creating an Icon or Other Image &#40;Image Editor for Icons&#41;](/visual-cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  