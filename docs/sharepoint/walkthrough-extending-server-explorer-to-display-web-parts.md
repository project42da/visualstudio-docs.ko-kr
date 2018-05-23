---
title: '연습: 웹 파트를 표시 하는 서버 탐색기 확장 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint commands
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 688c4d8d9193ec33f0dcb63923673826a453c9be
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-extending-server-explorer-to-display-web-parts"></a>연습: 서버 탐색기를 확장하여 웹 파트 표시
  Visual Studio에서 사용할 수 있습니다는 **SharePoint 연결** 의 노드 **서버 탐색기** SharePoint 사이트에서 구성 요소를 확인 합니다. 그러나 **서버 탐색기** 기본적으로 일부 구성 요소를 표시 하지 않습니다. 이 연습에서는 연장 됩니다 **서버 탐색기** SharePoint 사이트 각각 연결 된 웹 파트 갤러리에 표시 되도록 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   확장 하는 Visual Studio 확장을 만들 **서버 탐색기** 다음과 같은 방법으로:  
  
    -   확장을 통해 추가 된 **웹 파트 갤러리** 각 SharePoint 사이트 노드 아래의 노드 **서버 탐색기**합니다. 이 새 노드에 사이트에서 웹 파트 갤러리에서 각 웹 파트를 나타내는 자식 노드를 포함 합니다.  
  
    -   확장이 새로운 유형의 웹 파트 인스턴스를 나타내는 노드를 정의 합니다. 새 노드 형식은 기준으로 새 아래에 자식 노드 **웹 파트 갤러리** 노드. 새 웹 파트 노드 형식에 정보를 표시는 **속성** 나타내는 웹 파트에 대 한 창. 노드 형식에는 웹 파트와 관련 된 다른 작업을 수행 하기 위한 시작 지점으로 사용할 수 있는 사용자 지정 바로 가기 메뉴 항목을 포함 되어 있습니다.  
  
-   두 개의 사용자 지정 SharePoint 명령 만들기에서 확장 어셈블리 호출. SharePoint 명령에는 Api를 사용 하는 서버 개체 모델에서 SharePoint에 대 한 확장 프로그램 어셈블리를 호출할 수 있는 메서드입니다. 이 연습에서 개발 컴퓨터에서 로컬 SharePoint 사이트에서 웹 파트 정보를 검색 하는 명령을 만들 수 있습니다. 자세한 내용은 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
-   확장 배포를 확장 VSIX (Visual Studio) 패키지를 빌드하 합니다.  
  
-   디버깅 및 확장 테스트 합니다.  
  
> [!NOTE]  
>  다른 버전의 SharePoint 용 클라이언트 개체 모델을 사용 하 여 서버 개체 모델에 해당 하는 대신이 연습을 참조 하십시오. [연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 창, SharePoint 및 Visual Studio의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio SDK입니다. 이 연습에서는 **VSIX 프로젝트** 프로젝트 항목을 배포 하려면 VSIX 패키지를 만드는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   서버 개체 모델을 사용 하 여 SharePoint에 대 한 합니다. 자세한 내용은 참조 [SharePoint Foundation 서버 측 개체 모델을 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=177796)합니다.  
  
-   SharePoint 솔루션에서 웹 파트입니다. 자세한 내용은 참조 [웹 파트 개요](http://go.microsoft.com/fwlink/?LinkId=177803)합니다.  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 세 개의 프로젝트를 만들어야 합니다.  
  
-   확장 배포 하려면 VSIX 패키지를 만들려면 VSIX 프로젝트.  
  
-   확장을 구현 하는 클래스 라이브러리 프로젝트. 이 프로젝트는.NET Framework 4.5를 대상으로 해야 합니다.  
  
-   사용자 지정 SharePoint 명령을 정의 하는 클래스 라이브러리 프로젝트. 이 프로젝트는 the.NET Framework 3.5를 대상 해야 합니다.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후는 **확장성** 노드.  
  
    > [!NOTE]  
    >  **확장성** 노드를 Visual Studio SDK를 설치 하는 경우에 사용할 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 필수 구성 요소 섹션을 참조 하십시오.  
  
4.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
5.  선택 된 **VSIX 프로젝트** 서식 파일을 프로젝트 이름 **WebPartNode**, 선택한 후는 **확인** 단추 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **WebPartNode** 프로젝트를 **솔루션 탐색기**합니다.  
  
#### <a name="to-create-the-extension-project"></a>확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 노드 또는 **Visual Basic** 노드를 선택한 다음 선택 **Windows** 노드.  
  
3.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **클래스 라이브러리**, 프로젝트 이름을 **WebPartNodeExtension**를 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **WebPartNodeExtension** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>SharePoint 명령은 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 노드 또는 **Visual Basic** 노드를 선택한 후는 **Windows** 노드.  
  
3.  선택 대화 상자 맨 위에 있는 **.NET Framework 3.5** 버전의.NET Framework의 목록에 있습니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **클래스 라이브러리**, 프로젝트 이름을 **WebPartCommands**를 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **WebPartCommands** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
5.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-projects"></a>프로젝트 구성  
 확장을 만드는 데 코드를 작성 하기 전에 코드 파일 및 어셈블리 참조를 추가 하 고 프로젝트 설정을 구성 해야 합니다.  
  
#### <a name="to-configure-the-webpartnodeextension-project"></a>WebPartNodeExtension 프로젝트를 구성 하려면  
  
1.  WebPartNodeExtension 프로젝트에서 다음과 같은 이름의 네 개의 코드 파일을 추가 합니다.  
  
    -   SiteNodeExtension  
  
    -   WebPartNodeTypeProvider  
  
    -   WebPartNodeInfo  
  
    -   WebPartCommandIds  
  
2.  에 대 한 바로 가기 메뉴를 열고는 **WebPartNodeExtension** 프로젝트를 선택한 후 **참조 추가**합니다.  
  
3.  에 **참조 관리자-WebPartNodeExtension** 대화 상자에서 선택 하 고 **프레임 워크** 탭을 선택한 다음 각 다음 어셈블리에 대 한 확인란을 선택:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
4.  선택 된 **확장** 탭 Microsoft.VisualStudio.SharePoint 어셈블리에 대 한 확인란을 선택 하 고 선택 합니다는 **확인** 단추입니다.  
  
5.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **WebPartNodeExtension** 프로젝트 노드를 선택한 후 **속성**합니다.  
  
     **프로젝트 디자이너**가 열립니다.  
  
6.  **응용 프로그램** 탭을 선택합니다.  
  
7.  에 **기본 네임 스페이스** 상자 (C#) 또는 **루트 네임 스페이스** 상자 ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)])을 입력 **ServerExplorer.SharePointConnections.WebPartNode**합니다.  
  
#### <a name="to-configure-the-webpartcommands-project"></a>WebPartCommands 프로젝트를 구성 하려면  
  
1.  WebPartCommands 프로젝트에서 WebPartCommands 라는 코드 파일을 추가 합니다.  
  
2.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **WebPartCommands** 프로젝트 노드를 선택 **추가**를 선택한 후 **기존 항목**.  
  
3.  에 **기존 항목 추가** 대화 상자, WebPartNodeExtension 프로젝트에 대 한 코드 파일이 포함 된 폴더를 찾아 WebPartNodeInfo 및 WebPartCommandIds 코드 파일을 선택 합니다.  
  
4.  옆에 있는 화살표를 선택는 **추가** 단추를 선택한 후 **링크로 추가** 표시 되는 메뉴에 있습니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 링크로 WebPartCommands 프로젝트에 코드 파일을 추가합니다. 결과적으로, WebPartNodeExtension 프로젝트에서 코드 파일은 있지만 WebPartCommands 프로젝트에서 파일에 코드 파일도 컴파일됩니다.  
  
5.  에 대 한 바로 가기 메뉴를 열고는 **WebPartCommands** 다시 프로젝트를 마우스 선택 **참조 추가**합니다.  
  
6.  에 **참조 관리자-WebPartCommands** 대화 상자에서 선택 하는 **확장** 탭 각 다음 어셈블리에 대 한 확인란을 선택 하 고 선택 합니다는 **확인** button:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
7.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **WebPartCommands** 다시 프로젝트를 선택한 후 **속성**합니다.  
  
     **프로젝트 디자이너**가 열립니다.  
  
8.  **응용 프로그램** 탭을 선택합니다.  
  
9. 에 **기본 네임 스페이스** 상자 (C#) 또는 **루트 네임 스페이스** 상자 ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)])을 입력 **ServerExplorer.SharePointConnections.WebPartNode**합니다.  
  
## <a name="creating-icons-for-the-new-nodes"></a>새 노드에 대 한 아이콘 만들기  
 에 대 한 두 아이콘을 만듭니다는 **서버 탐색기** 확장: 새에 대 한 아이콘이 **웹 파트 갤러리** 노드와 각 자식 웹 파트 노드 아래에 대 한 다른 아이콘은 **웹 파트 갤러리** 노드입니다. 이 연습의 뒷부분에서는 이러한 아이콘 노드를 연결 하는 코드를 작성 합니다.  
  
#### <a name="to-create-icons-for-the-nodes"></a>노드에 대 한 아이콘을 만들려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **WebPartNodeExtension** 프로젝트를 선택한 후 **속성**합니다.  
  
2.  **프로젝트 디자이너**가 열립니다.  
  
3.  선택 된 **리소스** 탭을 선택 합니다는 **이 프로젝트는 기본 리소스 파일 포함 되어 있지 않습니다. 새로 만들려면 여기를 클릭 하십시오.** 링크 합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 리소스 파일을 만들고 디자이너에서 엽니다.  
  
4.  디자이너 맨 위에 있는 화살표를 옆에 선택 된 **리소스 추가** 메뉴 명령을 실행 하 고 다음 선택 **새 아이콘 추가** 나타나는 메뉴에서.  
  
5.  에 **새 리소스 추가** 대화 상자에서 이름 새로 만들기 아이콘 **WebPartsNode**를 선택한 후는 **추가** 단추입니다.  
  
     에 새로운 아이콘이 열리면는 **이미지 편집기**합니다.  
  
6.  쉽게 인식할 수 있는 디자인 있도록 16 x 16 버전의 아이콘을 편집 합니다.  
  
7.  아이콘의 32 x 32 버전에 대 한 바로 가기 메뉴를 열고 **이미지 형식 삭제**합니다.  
  
8.  5-8 프로젝트 자원에 두 번째 아이콘을 추가 단계를 반복 하 고이 아이콘을 이름을 **WebPart**합니다.  
  
9. **솔루션 탐색기**아래는 **리소스** 에 대 한 폴더는 **WebPartNodeExtension** 프로젝트에 대 한 바로 가기 메뉴를 열고, **WebPartsNode.ico**.  
  
10. 에 **속성** 창 옆에 있는 화살표를 선택 **빌드 작업**를 선택한 후 **포함 리소스** 나타나는 메뉴에서.  
  
11. 에 대 한 마지막 두 단계를 반복 **WebPart.ico**합니다.  
  
## <a name="adding-the-web-part-gallery-node-to-server-explorer"></a>서버 탐색기에 웹 파트 갤러리 노드 추가  
 새 추가 하는 클래스를 만들 **웹 파트 갤러리** 노드를 각 SharePoint 사이트 노드. 클래스가 구현 하 고 새 노드를 추가 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스입니다. 이 인터페이스를 구현 하 여 기존 노드의 동작을 확장 하려고 할 때마다 **서버 탐색기**, 노드를 자식 노드를 추가 하는 등입니다.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>서버 탐색기에 웹 파트 갤러리 노드를 추가 하려면  
  
1.  WebPartNodeExtension 프로젝트에서 SiteNodeExtension 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
    > [!NOTE]  
    >  이 코드를 추가, 프로젝트를 컴파일 오류 일부 있지만 자리를 비울 갈 후 추가 하면 코드 이후 단계에서.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="defining-a-node-type-that-represents-a-web-part"></a>웹 파트를 나타내는 노드 형식 정의  
 새로운 유형의 웹 파트를 나타내는 노드를 정의 하는 클래스를 만듭니다. Visual Studio 아래에 자식 노드를 표시 하려면이 새 노드 형식을 사용 하 여 **웹 파트 갤러리** 노드. 각 자식 노드에 SharePoint 사이트의 단일 웹 파트를 나타냅니다.  
  
 클래스가 구현 하는 새 노드 유형을 정의 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스입니다. 이 인터페이스를 구현 하는 새로운 유형의에서 노드를 정의 하려고 할 때마다 **서버 탐색기**합니다.  
  
#### <a name="to-define-the-web-part-node-type"></a>웹 파트 노드 형식을 정의 하려면  
  
1.  WebPartNodeExtension 프로젝트에서 WebPartNodeTypeProvder 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodetypeprovider.cs#2)]  
  
## <a name="defining-the-web-part-data-class"></a>웹 파트 데이터 클래스를 정의합니다.  
 SharePoint 사이트의 단일 웹 파트에 대 한 데이터를 포함 하는 클래스를 정의 합니다. 이 연습의 뒷부분에서 사이트에서 각 웹 파트에 대 한 데이터를 검색 한 다음이 클래스의 인스턴스로 데이터를 할당 하는 사용자 지정 SharePoint 명령에 만들어집니다.  
  
#### <a name="to-define-the-web-part-data-class"></a>웹 파트 데이터 클래스를 정의 하려면  
  
1.  WebPartNodeExtension 프로젝트에서 WebPartNodeInfo 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodeinfo.vb#3)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodeinfo.cs#3)]  
  
## <a name="defining-the-ids-for-the-sharepoint-command"></a>SharePoint 명령에 대 한 Id를 정의합니다.  
 사용자 지정 SharePoint 명령을 식별 하는 여러 문자열을 정의 합니다. 이 연습의 뒷부분에서는 이러한 명령을 구현 합니다.  
  
#### <a name="to-define-the-command-ids"></a>명령 Id를 정의 하려면  
  
1.  WebPartNodeExtension 프로젝트에서 WebPartCommandIds 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartcommandids.cs#4)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartcommandids.vb#4)]  
  
## <a name="creating-the-custom-sharepoint-commands"></a>사용자 지정 SharePoint 명령 만들기  
 SharePoint 사이트에서 웹 파트에 대 한 데이터를 검색 하는 SharePoint에 대 한 서버 개체 모델을 호출 하는 사용자 지정 명령을 만듭니다. 각 명령은 변수가 있는 메서드에 <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> 적용할 수 있습니다.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint 명령을 정의 하려면  
  
1.  WebPartCommands 프로젝트에서 WebPartCommands 코드 파일을 연 후 다음 코드를 붙여 넣습니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/CSharp/WebPartNode/WebPartCommands/WebPartCommands.cs#6)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartcommands/webpartcommands.vb#6)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 연습에 대 한 모든 코드는 **웹 파트 갤러리** 노드와 SharePoint 명령은 현재 위치는 프로젝트입니다. 해당 오류 없이 두 프로젝트를 컴파일하여 되도록 솔루션을 빌드하십시오.  
  
#### <a name="to-build-the-solution"></a>솔루션을 빌드하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
    > [!WARNING]  
    >  이 시점에서 VSIX 매니페스트 파일 작성자에 대 한 값을가 되지 않았으므로 WebPartNode 프로젝트 빌드 오류에 있을 수 있습니다. 이 오류는 사라집니다 이후 단계에서 값을 추가 합니다.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>확장 배포 하려면 VSIX 패키지 만들기  
 확장을 배포 하려면 솔루션에서 VSIX 프로젝트를 사용 하 여 VSIX 패키지를 만듭니다. 첫째, VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다. 그런 다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### <a name="to-configure-the-vsix-package"></a>VSIX 패키지를 구성 하려면  
  
1.  **솔루션 탐색기**, WebPartNode 프로젝트에서 열고는 **source.extension.vsixmanifest** 매니페스트 편집기에서 파일입니다.  
  
     Source.extension.vsixmanifest 파일은 필요한 모든 VSIX 패키지 extension.vsixmanifest 파일의 기준이 됩니다. 이 파일에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다.  
  
2.  에 **제품 이름** 상자에 입력 **서버 탐색기에 대 한 웹 파트 갤러리 노드**합니다.  
  
3.  에 **작성자** 상자에 입력 **Contoso**합니다.  
  
4.  에 **설명** 상자에 입력 **사용자 지정 웹 파트 갤러리 노드 서버 탐색기에서 SharePoint 연결 노드를 추가 합니다. 이 확장 서버 개체 모델을 호출 하는 사용자 지정 SharePoint 명령을 사용 합니다.**  
  
5.  선택 된 **자산** 편집기의 탭 선택한 후는 **새로 만들기** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
6.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `MefComponent` extension.vsixmanifest 파일의 요소입니다. 이 요소는 VSIX 패키지의 확장 어셈블리의 이름을 지정합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
7.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
8.  에 **프로젝트** 목록에서 선택 **WebPartNodeExtension** 선택한 후는 **확인** 단추입니다.  
  
9. 매니페스트 편집기에서 선택 된 **새로** 단추를 다시 합니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
10. 에 **형식** 상자에 입력 **SharePoint.Commands.v4**합니다.  
  
    > [!NOTE]  
    >  이 요소는 Visual Studio 확장에 포함 하려는 사용자 지정 확장을 지정 합니다. 자세한 내용은 참조 [자산 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737)합니다.  
  
11. 에 **소스** 목록에서 선택 된 **현재 솔루션의 프로젝트** 목록 항목입니다.  
  
12. 에 **프로젝트** 목록에서 선택 **WebPartCommands**를 선택한 후는 **확인** 단추입니다.  
  
13. 메뉴 모음에서 **빌드**, **솔루션 빌드**, 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
14. WebPartNode 프로젝트에 대 한 빌드 출력 폴더 WebPartNode.vsix 파일을 이제 포함 되어 있는지 확인 합니다.  
  
     빌드 출력 폴더는 기본적으로는... 프로젝트 파일에 포함 된 폴더 아래 \bin\Debug 폴더입니다.  
  
## <a name="testing-the-extension"></a>확장 테스트  
 이제 새 테스트 준비가 **웹 파트 갤러리** 노드에서 **서버 탐색기**합니다. 먼저 Visual Studio의 실험적 인스턴스에서 확장 디버깅을 시작 합니다. 그런 다음 사용 하는 새 **웹 파트** 실험적 인스턴스의 노드 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
#### <a name="to-start-debugging-the-extension"></a>확장 프로그램 디버깅을 시작 하려면  
  
1.  다시 시작 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 관리 자격 증명 및 WebPartNode 솔루션을 엽니다.  
  
2.  WebPartNodeExtension 프로젝트에서 SiteNodeExtension 코드 파일을 열고 다음 코드의 첫 번째 줄에 중단점을 추가 `NodeChildrenRequested` 및 `CreateWebPartNodes` 메서드.  
  
3.  F5 키를 선택하여 디버깅을 시작합니다.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web 파트 갤러리 노드 확장을 서버 Explorer\1.0에 대 한 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-extension"></a>확장을 테스트 하려면  
  
1.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 모음에서 **보기**, **서버 탐색기**합니다.  
  
2.  테스트에 사용할 SharePoint 사이트에서 표시 되지 않으면 다음 단계는 **SharePoint 연결** 노드에서 **서버 탐색기**:  
  
    1.  **서버 탐색기**, 바로 가기 메뉴를 열고 **SharePoint 연결**를 선택한 후 **연결 추가**합니다.  
  
    2.  에 **SharePoint 연결 추가** 대화 상자에서 다음을 선택 하 고 연결할 SharePoint 사이트에 대 한 URL을 입력에서 **확인** 단추입니다.  
  
         개발 컴퓨터에 SharePoint 사이트를 지정 하려면 입력 **http://localhost**합니다.  
  
3.  (표시 하는 사이트의 URL) 사이트 연결 노드를 확장 한 후 자식 사이트 노드를 확장 (예를 들어 **팀 사이트**).  
  
4.  확인 코드의 다른 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 이전에 설정한 중단점에서 중지는 `NodeChildrenRequested` 메서드를 계속 프로젝트를 디버그 하려면 f5 키를 선택 합니다.  
  
5.  Visual Studio의 실험적 인스턴스에서 이라는 새 노드가 있는지를 확인 **웹 파트 갤러리** 최상위 사이트 노드 아래에 표시 한 다음 확장은 **웹 파트 갤러리** 노드.  
  
6.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `CreateWebPartNodes` 메서드를 계속 프로젝트를 디버그 하려면 F5 키를 선택 합니다.  
  
7.  Visual Studio의 실험적 인스턴스에서 연결된 된 사이트의 모든 웹 파트에 나타나는지 확인는 **웹 파트 갤러리** 노드에서 **서버 탐색기**합니다.  
  
8.  **서버 탐색기**, 웹 파트 중 하나에 대 한 바로 가기 메뉴를 열고 선택한 후 **속성**합니다.  
  
9. 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디버그 중인, 웹 파트에 대 한 세부 정보에 표시 되는지 확인은 **속성** 창.  
  
## <a name="uninstalling-the-extension-from-visual-studio"></a>Visual Studio에서 확장을 제거합니다.  
 확장 테스트를 마친 후 Visual Studio에서 확장을 제거 합니다.  
  
#### <a name="to-uninstall-the-extension"></a>확장을 제거하려면  
  
1.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 모음에서 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택 **서버 탐색기에 대 한 웹 파트 갤러리 노드 확장**를 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택은 **예** 단추에서 확장을 제거 하 고 다음을 선택 하도록 확인할 수는 **지금 다시 시작** 단추 제거를 완료 합니다.  
  
4.  Visual Studio (실험적 인스턴스 및 WebPartNode 솔루션 열릴 Visual Studio의 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)   
 [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)   
 [아이콘 또는 다른 이미지 만들기 &#40;아이콘에 대 한 이미지 편집기&#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  