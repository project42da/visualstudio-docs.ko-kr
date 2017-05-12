---
title: "Walkthrough: Extending Server Explorer to Display Web Parts"
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
  - "SharePoint Connections [SharePoint development in Visual Studio], extending a node"
  - "SharePoint commands"
  - "SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer"
  - "SharePoint Connections [SharePoint development in Visual Studio], creating a new node type"
ms.assetid: 5b1f104a-0eaf-4929-9f1f-d7afcfc8b707
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# Walkthrough: Extending Server Explorer to Display Web Parts
  Visual Studio 사용할 수 있는  **SharePoint 연결** 노드를  **서버 탐색기** 구성 SharePoint 사이트에서 볼 수.  그러나  **서버 탐색기** 일부 구성 요소는 기본적으로 표시 되지 않습니다.  이 연습에서는 사용자를 확장할 것  **서버 탐색기** SharePoint 사이트 웹 파트 갤러리에 표시 되도록 연결 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   다음과 같은 방법으로 **서버 탐색기**를 확장하는 Visual Studio 확장 만들기  
  
    -   확장명 추가 된  **웹 파트 갤러리** 노드 아래에서 각 SharePoint 사이트 노드의  **서버 탐색기**.  새 노드에는 사이트에서 웹 파트 갤러리의 각 웹 파트를 나타내는 자식 노드가 포함됩니다.  
  
    -   확장 웹 파트 인스턴스를 나타내는 노드의 새 형식을 정의 합니다.  새 노드 형식은 새 **웹 파트 갤러리** 노드 아래에 있는 자식 노드의 기반이 됩니다.  새 웹 파트 노드 형식이 나타내는 웹 파트에 대한 정보가 **속성** 창에 표시됩니다.  노드 형식에는 웹 파트와 관련 된 다른 작업을 수행 하는 데 시작 점으로 사용할 수 있는 사용자 지정 바로 가기 메뉴 항목을 포함 되어 있습니다.  
  
-   두 개의 사용자 지정 SharePoint 명령을 만들기는 확장 어셈블리 호출 합니다.  SharePoint 명령을 확장 어셈블리에 대 한 SharePoint 서버 개체 모델의 Api를 사용 하 여 호출할 수 있는 메서드입니다.  이 연습에서는 개발 컴퓨터의 로컬 SharePoint 사이트로부터 웹 파트 정보를 검색하는 명령을 만듭니다.  자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
-   확장을 배포하기 위한 VSIX\(Visual Studio Extension\) 패키지 빌드  
  
-   확장 디버깅 및 테스트  
  
> [!NOTE]  
>  해당 서버 개체 모델 대신 Sharepoint에 대 한 클라이언트 개체 모델을 사용 하는이 연습에서 대체 버전을 참조 하십시오. [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## 사전 요구 사항  
 이 연습을 완료하려면 개발 컴퓨터에 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전의 Windows, SharePoint 및 Visual Studio.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio SDK입니다.  이 연습에서는 SDK의 **VSIX 프로젝트** 템플릿을 사용하여 프로젝트 항목을 배포하기 위한 VSIX 패키지를 만듭니다.  자세한 내용은 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
 다음 개념을 알고 있으면 연습을 완료하는 데 도움이 되지만 반드시 필요하지는 않습니다.  
  
-   Sharepoint에 대 한 서버 개체 모델을 사용 합니다.  자세한 내용은 [Using the SharePoint Foundation Server\-Side Object Model](http://go.microsoft.com/fwlink/?LinkId=177796)을 참조하십시오.  
  
-   SharePoint 솔루션의 웹 파트.  자세한 내용은 [Web Parts Overview](http://go.microsoft.com/fwlink/?LinkId=177803)를 참조하십시오.  
  
## 프로젝트 만들기  
 이 연습을 완료 하려면 세 프로젝트를 만들어야 합니다.  
  
-   VSIX 패키지를 만들어 확장을 배포하기 위한 VSIX 프로젝트  
  
-   확장을 구현하는 클래스 라이브러리 프로젝트.  .NET Framework 4.5이이 프로젝트를 대상으로 해야 합니다.  
  
-   사용자 지정 SharePoint 명령을 정의하는 클래스 라이브러리 프로젝트.  이 프로젝트는 .NET Framework 3.5를 대상으로 해야 합니다.  
  
 먼저 프로젝트를 만들어 연습을 시작합니다.  
  
#### VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
3.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 또는  **Visual Basic** 노드를 다음 선택은  **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드인 Visual Studio SDK를 설치한 경우에 사용할 수 있습니다.  자세한 내용은 이 항목의 앞부분에 나오는 사전 요구 사항 단원을 참조하십시오.  
  
4.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
5.  선택은  **VSIX 프로젝트** 템플릿, 프로젝트 이름  **WebPartNode**, 다음 선택은  **확인** 단추.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **WebPartNode** 프로젝트를 추가합니다.  
  
#### 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, 솔루션 노드 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장 된  **C\#** 노드 또는  **Visual Basic** 노드를 선택한 다음 선택  **Windows** 노드.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 4.5** .NET Framework 버전의 목록에서입니다.  
  
4.  프로젝트 템플릿 목록에서 선택  **클래스 라이브러리**, 프로젝트의 이름을  **WebPartNodeExtension**, 다음 선택은  **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **WebPartNodeExtension** 프로젝트를 추가하고 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
#### SharePoint 명령 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, 솔루션 노드 바로 가기 메뉴를 열고  **추가**, 다음 선택  **새 프로젝트**.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서는 [NIB: General, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)에서 **솔루션 항상 표시** 확인란을 선택한 경우에만 **솔루션 탐색기**에 솔루션 노드가 표시됩니다.  
  
2.  에  **새 프로젝트** 대화 상자에서 확장은  **C\#** 노드 또는  **Visual Basic** 노드를 다음 선택은  **Windows** 노드.  
  
3.  대화 상자의 맨 위에 있는 선택  **.NET Framework 3.5** .NET Framework 버전의 목록에서입니다.  
  
4.  프로젝트 템플릿 목록에서 선택  **클래스 라이브러리**, 프로젝트의 이름을  **WebPartCommands**, 다음 선택은  **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 솔루션에 **WebPartCommands** 프로젝트를 추가하고 기본 Class1 클래스 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제합니다.  
  
## 프로젝트 구성  
 확장을 만드는 코드를 작성 하기 전에 코드 파일과 어셈블리 참조를 추가 하 고 프로젝트 설정을 구성 해야 합니다.  
  
#### WebPartNodeExtension 프로젝트를 구성하려면  
  
1.  WebPartNodeExtension 프로젝트에 다음과 같은 이름을 가진 네 개의 코드 파일을 추가 합니다.  
  
    -   SiteNodeExtension  
  
    -   WebPartNodeTypeProvider  
  
    -   WebPartNodeInfo  
  
    -   WebPartCommandIds  
  
2.  바로 가기 메뉴를 열고를  **WebPartNodeExtension** 프로젝트를 하 고 선택  **참조 추가**.  
  
3.  에  **참조 관리자 – WebPartNodeExtension** 대화 상자에서 선택 된  **프레임 워크** 탭을 클릭 한 다음 각 다음 어셈블리에 대 한 확인란을 선택:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
4.  선택은  **확장명** 탭 Microsoft.VisualStudio.SharePoint 어셈블리에 대 한 확인란을 선택 하 고 다음을 선택의  **확인** 단추.  
  
5.  **솔루션 탐색기**, 바로 가기 메뉴를 열고를  **WebPartNodeExtension** 프로젝트 노드 및 다음 선택  **속성**.  
  
     **프로젝트 디자이너**가 열립니다.  
  
6.  선택 된  **응용 프로그램** 탭입니다.  
  
7.  에  **기본 네임 스페이스** 상자 \(C\#\) 또는  **루트 네임 스페이스** 상자 \([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]\)를 입력  **ServerExplorer.SharePointConnections.WebPartNode**.  
  
#### WebPartCommands 프로젝트를 구성하려면  
  
1.  WebPartCommands 프로젝트에서 WebPartCommands 라는 코드 파일을 추가 합니다.  
  
2.  **솔루션 탐색기**, 바로 가기 메뉴를 열고를  **WebPartCommands** 프로젝트 노드를 선택  **추가**, 다음 선택  **기존 항목**.  
  
3.  에 있는  **기존 항목 추가** 대화 상자 WebPartNodeExtension 프로젝트에 대 한 코드 파일이 들어 있는 폴더를 찾습니다 및 다음 WebPartNodeInfo 및 WebPartCommandIds 코드 파일을 선택 합니다.  
  
4.  옆에 있는 화살표를 선택한는  **추가** 단추를 클릭 한 다음 선택  **링크로 추가** 에 표시 되는 메뉴.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 코드 파일을 WebPartCommands 프로젝트에 링크로 추가합니다.  결과적으로 WebPartNodeExtension 프로젝트에 코드 파일이 있습니다 하지만 코드 파일에서 또한 WebPartCommands 프로젝트의 컴파일.  
  
5.  바로 가기 메뉴를 열고를  **WebPartCommands** 다시, 프로젝트 및 선택  **참조 추가**.  
  
6.  에  **참조 관리자 – WebPartCommands** 대화 상자에서 선택에서  **확장** 탭, 각각 다음 어셈블리에 대 한 확인란을 선택 하 고 다음을 선택의  **확인** 단추:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
7.  **솔루션 탐색기**, 바로 가기 메뉴를 열고를  **WebPartCommands** 프로젝트를 다시 및 다음 선택  **속성**.  
  
     **프로젝트 디자이너**가 열립니다.  
  
8.  선택 된  **응용 프로그램** 탭입니다.  
  
9. 에  **기본 네임 스페이스** 상자 \(C\#\) 또는  **루트 네임 스페이스** 상자 \([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]\)를 입력  **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## 새 노드의 아이콘 만들기  
 **서버 탐색기** 확장에 대한 두 아이콘을 만듭니다. 한 아이콘은 새 **웹 파트 갤러리** 노드를 나타내고, 다른 아이콘은 **웹 파트 갤러리** 노드 아래의 각 자식 웹 파트 노드를 나타냅니다.  이 연습의 뒷부분에서는 이러한 아이콘을 노드에 연결하는 코드를 작성합니다.  
  
#### 노드의 아이콘을 만들려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고를  **WebPartNodeExtension** 프로젝트를 하 고 선택  **속성**.  
  
2.  **프로젝트 디자이너**가 열립니다.  
  
3.  선택은  **리소스** 탭을 클릭 한 다음 선택은  **이 프로젝트에는 기본 리소스 파일이 없습니다. 여기를 클릭 하 여 파일을 만들려면** 링크입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]리소스 파일을 만들고 디자이너에서 열립니다.  
  
4.  디자이너의 맨 위에 있는 화살표 옆에 선택 된  **리소스 추가** 메뉴, 명령을 클릭 한 다음 선택  **새 아이콘 추가** 나타나는 메뉴에서.  
  
5.  에  **새 리소스 추가** 이름 새 아이콘 대화 상자에서  **WebPartsNode**, 다음 선택은  **추가** 단추.  
  
     새 아이콘이 **이미지 편집기**에서 열립니다.  
  
6.  디자인을 쉽게 인식할 수 있도록 16x16 버전의 아이콘 편집 합니다.  
  
7.  32X32 버전의 아이콘, 바로 가기 메뉴를 열고 선택  **이미지 형식 삭제**.  
  
8.  5 단계에서 두 번째 아이콘은 프로젝트 리소스에 추가 하는 8 단계를 반복 하 고이 아이콘 이름을  **WebPart**.  
  
9. **솔루션 탐색기**아래에서  **리소스** 폴더에는  **WebPartNodeExtension** 프로젝트에 대 한 바로 가기 메뉴를 엽니다  **WebPartsNode.ico**.  
  
10. 에  **속성** 창 옆에 있는 화살표를 선택한  **빌드 작업**, 다음 선택  **포함 리소스** 나타나는 메뉴입니다.  
  
11. **WebPart.ico**에 대해 마지막 두 단계를 반복합니다.  
  
## 서버 탐색기에 웹 파트 갤러리 노드 추가  
 각 SharePoint 사이트 노드에 새 **웹 파트 갤러리** 노드를 추가하는 클래스를 만듭니다.  새 코드를 추가하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스를 구현합니다.  기존 노드의 동작을 확장 하려는 경우이 인터페이스를 구현  **서버 탐색기**, 같은 노드에 자식 노드를 추가 합니다.  
  
#### 서버 탐색기에 웹 파트 갤러리 노드를 추가하려면  
  
1.  WebPartNodeExtension 프로젝트에 SiteNodeExtension 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
    > [!NOTE]  
    >  때이 코드를 추가 하 여, 프로젝트 일부 컴파일 오류가 있지만 없어질 것 후 코드 이후 단계에서 추가 합니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/CS/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/vb/webpartnodeextension/sitenodeextension.vb#1)]  
  
## 웹 파트를 나타내는 노드 형식 정의  
 웹 파트를 나타내는 새 노드 형식을 정의하는 클래스를 만듭니다.  Visual Studio 새 노드 형식을 사용 하 여 아래에서 자식 노드를 표시 하는  **웹 파트 갤러리** 노드.  단일 웹 파트는 SharePoint 사이트의 각 자식 노드를 나타냅니다.  
  
 새 노드 형식을 정의하기 위해 클래스에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스를 구현합니다.  **서버 탐색기**에서 새 노드 형식을 정의하려는 경우 이 인터페이스를 구현합니다.  
  
#### 웹 파트 노드 형식을 정의하려면  
  
1.  WebPartNodeExtension 프로젝트에 WebPartNodeTypeProvder 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/CS/webpartnodeextension/webpartnodetypeprovider.cs#2)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/vb/webpartnodeextension/webpartnodetypeprovider.vb#2)]  
  
## 웹 파트 데이터 클래스 정의  
 SharePoint 사이트의 단일 웹 파트에 대한 정보가 포함된 클래스를 정의합니다.  이 연습의 뒷부분에서 각 웹 파트는 사이트에 대 한 데이터를 검색 하 고 다음이 클래스의 인스턴스에 데이터를 할당 하는 사용자 지정 SharePoint 명령을 만듭니다.  
  
#### 웹 파트 데이터 클래스를 정의하려면  
  
1.  WebPartNodeExtension 프로젝트에 WebPartNodeInfo 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/CS/webpartnodeextension/webpartnodeinfo.cs#3)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/vb/webpartnodeextension/webpartnodeinfo.vb#3)]  
  
## SharePoint 명령의 ID 정의  
 사용자 지정 SharePoint 명령을 식별하는 여러 문자열을 정의합니다.  이러한 명령은 이 연습의 뒷부분에서 구현합니다.  
  
#### 명령 ID를 정의하려면  
  
1.  WebPartNodeExtension 프로젝트에 WebPartCommandIds 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/CS/webpartnodeextension/webpartcommandids.cs#4)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/vb/webpartnodeextension/webpartcommandids.vb#4)]  
  
## 사용자 지정 SharePoint 명령 만들기  
 웹 파트 SharePoint 사이트에 대 한 데이터를 검색 하려면 SharePoint 서버 개체 모델을 호출 하는 사용자 지정 명령을 만듭니다.  각 명령은 <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute>가 적용된 메서드입니다.  
  
#### SharePoint 명령을 정의하려면  
  
1.  WebPartCommands 프로젝트에 WebPartCommands 코드 파일을 열고 다음 코드를 붙여넣은 다음 다음.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/CS/WebPartCommands/WebPartCommands.cs#6)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.spexplorer.webpartnodewithcommands/vb/webpartcommands/webpartcommands.vb#6)]  
  
## 검사점  
 이 연습의 이전 단계를 통해 **웹 파트 갤러리** 노드와 SharePoint 명령을 위한 모든 코드가 프로젝트에 포함되었습니다.  솔루션을 빌드하여 두 프로젝트가 오류 없이 컴파일되는지 확인합니다.  
  
#### 솔루션을 빌드하려면  
  
1.  메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**.  
  
    > [!WARNING]  
    >  이 시점에서 VSIX 매니페스트 파일 작성자에 대 한 값을 포함 하지 않으므로 WebPartNode 프로젝트 빌드 오류가 있을 수 있습니다.  이후 단계에서 값을 추가 하면이 오류가 사라집니다.  
  
## 확장을 배포하기 위한 VSIX 패키지 만들기  
 확장을 배포하려면 솔루션에서 VSIX 프로젝트를 사용하여 VSIX 패키지를 만듭니다.  첫째, VSIX 프로젝트에 있는 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다.  그런 다음 솔루션을 빌드하여 VSIX 패키지를 만듭니다.  
  
#### VSIX 패키지를 구성하려면  
  
1.  **솔루션 탐색기**, WebPartNode 프로젝트에서 열은  **source.extension.vsixmanifest** 파일이 매니페스트 편집기에서.  
  
     Source.extension.vsixmanifest 파일이 모든 VSIX 패키지를 요구 하는 extension.vsixmanifest 파일에 대 한 기반이 됩니다.  이 파일에 대한 자세한 내용은 [VSIX 확장 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)를 참조하십시오.  
  
2.  에 있는  **제품명** 상자에 입력  **서버 탐색기에 웹 파트 갤러리 노드**.  
  
3.  에 있는  **작성자** 상자에 입력  **Contoso**.  
  
4.  에  **설명** 상자에 입력  **서버 탐색기에서의 SharePoint 연결 노드에 사용자 지정 웹 파트 갤러리 노드를 추가 합니다. 이 확장에서는 사용자 지정 SharePoint 명령을 사용하여 서버 개체 모델을 호출합니다.**라고 입력합니다.  
  
5.  선택은  **자산** 편집기의 탭 다음 선택은  **New** 단추.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
6.  에 있는  **유형** 목록에서 선택  **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  이 값은 extension.vsixmanifest 파일의 `MefComponent` 요소에 해당합니다.  이 요소는 VSIX 패키지의 확장 어셈블리 이름을 지정합니다.  자세한 내용은 [NIB: MEFComponent Element \(VSX Schema\)](http://msdn.microsoft.com/ko-kr/8a813141-8b73-44c9-b80b-ca85bbac9551)을 참조하십시오.  
  
7.  에 있는  **원본** 목록에서 선택  **현재 솔루션의 프로젝트에**.  
  
8.  에  **프로젝트** 목록에서 선택  **WebPartNodeExtension** 다음 선택은  **확인** 단추입니다.  
  
9. 매니페스트 편집기에서 선택 된  **New** 단추를 다시 클릭 합니다.  
  
     **를 추가 하는 새로운 자산** 대화 상자가 나타납니다.  
  
10. 에 있는  **유형** 상자에 입력  **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  이 요소는 Visual Studio 확장에 포함할 사용자 지정 확장을 지정합니다.  자세한 내용은 [자산 요소 \(VSX 스키마\)](http://msdn.microsoft.com/ko-kr/9fcfc098-edc7-484b-9d4c-acd17829d737)을 참조하십시오.  
  
11. 에  **소스** 목록에서 선택 된  **현재 솔루션의 프로젝트에** 목록 항목.  
  
12. 에  **프로젝트** 목록에서 선택  **WebPartCommands**, 다음 선택은  **확인** 단추입니다.  
  
13. 메뉴 표시줄에서 선택  **빌드**,  **솔루션 빌드**, 및 다음 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
14. WebPartNode 프로젝트의 빌드 출력 폴더에 이제 WebPartNode.vsix 파일이 들어 있는지 확인 합니다.  
  
     기본적으로 빌드 출력 경로는 프로젝트 파일이 포함된 폴더 아래에 있는 ..  \\bin\\Debug 폴더입니다.  
  
## 확장 테스트  
 이제 새 테스트할 준비가  **웹 파트 갤러리** 노드에서  **서버 탐색기**.  우선 실험 모드의 Visual Studio 인스턴스에서 확장을 디버깅합니다.  그런 다음 실험 모드의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 인스턴스에 새 **웹 파트** 노드를 사용합니다.  
  
#### 확장 디버깅을 시작하려면  
  
1.  다시 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 관리 자격 증명 및 다음 열기 WebPartNode 솔루션입니다.  
  
2.  WebPartNodeExtension 프로젝트에 SiteNodeExtension 코드 파일을 열고 다음 코드의 첫째 줄에 중단점을 추가 된 `NodeChildrenRequested` 및 `CreateWebPartNodes` 방법.  
  
3.  F5 키를 선택하여 디버깅을 시작합니다.  
  
     Visual Studio 서버 explorer\\1.0에 대해 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0Exp\\Extensions\\Contoso\\Web 파트 갤러리 노드를 확장 하 여 확장을 설치 하 고 Visual Studio 실험 인스턴스를 시작 합니다.  이 Visual Studio 인스턴스에서 프로젝트 항목을 테스트합니다.  
  
#### 확장을 테스트하려면  
  
1.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 표시줄에서 선택  **보기**,  **서버 탐색기**.  
  
2.  테스트 하는 데 사용 하려는 SharePoint 사이트 아래 나타나지 않으면 다음 단계를 수행은  **SharePoint 연결** 노드에서  **서버 탐색기**.  
  
    1.  **서버 탐색기**, 바로 가기 메뉴를 열고  **SharePoint 연결**, 다음 선택  **연결 추가**.  
  
    2.  에 있는  **SharePoint 연결 추가** 대화 상자에서 적용할 연결, 및 다음 선택 하려면 SharePoint 사이트에 대 한 URL을 입력의  **확인** 단추.  
  
         개발 컴퓨터에서 SharePoint 사이트를 지정 하려면 입력  **http:\/\/localhost**.  
  
3.  사이트의 URL을 표시 하 고 사이트 연결 노드를 확장 한 다음 자식 사이트 노드를 확장 합니다 \(예를 들어,  **팀 사이트**\).  
  
4.  확인 코드의 다른 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 이전에 설정한 중단점에서 중지는 `NodeChildrenRequested` 메서드를 다음 프로젝트에 디버깅을 계속 하려면 f5 키를 선택 합니다.  
  
5.  새 노드 라는 Visual Studio 실험적 인스턴스에서 확인  **웹 파트 갤러리** 최상위 사이트 노드 아래에 표시 한 다음 확장 된  **웹 파트 갤러리** 노드.  
  
6.  코드 Visual Studio 인스턴스를 이전에 설정한 중단점에서 중지 하는지 확인은 `CreateWebPartNodes` 메서드를 다음 프로젝트에 디버깅을 계속 하려면 F5 키를 선택 합니다.  
  
7.  Visual Studio 실험적 인스턴스에서 연결된 된 사이트의 모든 웹 파트 나타나는지 확인은  **웹 파트 갤러리** 노드에서  **서버 탐색기**.  
  
8.  **서버 탐색기**, 웹 파트 중 하나에 대 한 바로 가기 메뉴를 엽니다 및 다음 선택  **속성이**.  
  
9. 인스턴스의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버깅 하 고, 세부 정보 웹 파트에 표시 되는지 확인은  **속성이** 창.  
  
## Visual Studio에서 확장 제거  
 확장 테스트를 마친 후 Visual Studio에서 확장을 제거합니다.  
  
#### 확장을 제거하려면  
  
1.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 표시줄에서 선택  **도구**,  **확장 및 업데이트**.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장명 목록에서 선택한  **서버 탐색기에 웹 파트 갤러리 노드 확장**, 다음 선택은  **제거** 단추입니다.  
  
3.  나타나는 대화 상자에서 선택 된  **예** 확장명을 제거 하 고 선택 확인 단추는  **지금 다시 시작** 단추 제거를 완료 합니다.  
  
4.  Visual Studio \(Visual Studio WebPartNode 솔루션에 열려 있는 인스턴스 및 실험적 인스턴스\)을 모두 닫습니다.  
  
## 참고 항목  
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)   
 [Image Editor for Icons](/visual-cpp/windows/image-editor-for-icons)   
 [Creating an Icon or Other Image &#40;Image Editor for Icons&#41;](/visual-cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  