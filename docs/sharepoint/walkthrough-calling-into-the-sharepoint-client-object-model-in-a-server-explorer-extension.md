---
title: '연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, client object model
- SharePoint commands [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4951d9960a3027e8d72bb0fbc72d551f123993ce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension"></a>연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출
  이 연습에 대 한 확장에서 SharePoint 클라이언트 개체 모델을 호출 하는 방법을 보여 줍니다는 **SharePoint 연결** 노드에서 **서버 탐색기**합니다. SharePoint 클라이언트 개체 모델을 사용 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   만들기는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 확장을 확장 하 고 **SharePoint 연결** 의 노드 **서버 탐색기** 다음과 같은 방법으로:  
  
    -   확장을 통해 추가 된 **웹 파트 갤러리** 각 SharePoint 사이트 노드 아래의 노드 **서버 탐색기**합니다. 이 새 노드에 사이트에서 웹 파트 갤러리에서 각 웹 파트를 나타내는 자식 노드를 포함 합니다.  
  
    -   확장이 새로운 유형의 웹 파트 인스턴스를 나타내는 노드를 정의 합니다. 새 노드 형식은 기준으로 새 아래에 자식 노드 **웹 파트 갤러리** 노드. 새 웹 파트 노드 형식에 정보를 표시는 **속성** 노드에서 나타내는 웹 파트에 대 한 창.  
  
-   확장 배포를 확장 VSIX (Visual Studio) 패키지를 빌드하 합니다.  
  
-   디버깅 및 확장 테스트 합니다.  
  
> [!NOTE]  
>  이 연습에서 만든 확장 프로그램에서 만드는 확장 유사한 [연습: 디스플레이 웹 파트를 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다. 해당 연습에서는 SharePoint 서버 개체 모델을 사용 하지만이 연습에서는 클라이언트 개체 모델을 사용 하 여 동일한 작업을 수행 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료 하려면 개발 컴퓨터에 다음 구성 요소가 필요 합니다.  
  
-   지원 되는 Windows, SharePoint 및 Visual Studio의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio SDK입니다. 이 연습에서는 **VSIX 프로젝트** VSIX 패키지 확장 배포를 만들려는 SDK에서 서식 파일입니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
다음 개념을 이해에 도움이 되지만 필수는 아니므로 연습을 완료 하는:  
  
-   SharePoint 클라이언트 개체 모델을 사용 합니다. 자세한 내용은 참조 [관리 되는 클라이언트 개체 모델](http://go.microsoft.com/fwlink/?LinkId=177797)합니다.  
  
-   Sharepoint에서 웹 파트입니다. 자세한 내용은 참조 [웹 파트 개요](http://go.microsoft.com/fwlink/?LinkId=177803)합니다.  
  
## <a name="creating-the-projects"></a>프로젝트 만들기  
 이 연습을 완료 하려면 두 개의 프로젝트를 만들어야 합니다.  
  
-   VSIX 프로젝트를 만들려면 VSIX 패키지를 배포 하는 **서버 탐색기** 확장 합니다.  
  
-   구현 하는 클래스 라이브러리 프로젝트는 **서버 탐색기** 확장 합니다.  
  
 이 연습에서는 먼저 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후 **확장성**합니다.  
  
    > [!NOTE]  
    >  **확장성** 노드를 Visual Studio SDK를 설치 하는 경우에 사용할 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 필수 구성 요소 섹션을 참조 하십시오.  
  
4.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
     SharePoint 도구 확장에는이 버전의.NET Framework의 기능이 필요 합니다.  
  
5.  선택 된 **VSIX 프로젝트** 템플릿.  
  
6.  에 **이름** 상자에 입력 합니다 **WebPartNode**를 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **WebPartNode** 프로젝트를 **솔루션 탐색기**합니다.  
  
#### <a name="to-create-the-extension-project"></a>확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**솔루션 노드에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후 **Windows**합니다.  
  
3.  선택 대화 상자 맨 위에 있는 **.NET Framework 4.5** 버전의.NET Framework의 목록에 있습니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **클래스 라이브러리**합니다.  
  
5.  에 **이름** 상자에 입력 **WebPartNodeExtension**, 선택한 후는 **확인** 단추입니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **WebPartNodeExtension** 프로젝트를 솔루션 기본 Class1 코드 파일을 엽니다.  
  
6.  프로젝트에서 Class1 코드 파일을 삭제 합니다.  
  
## <a name="configuring-the-extension-project"></a>확장 프로젝트 구성  
 확장을 만드는 데 코드를 작성 하기 전에 코드 파일 및 어셈블리 참조를 프로젝트에 추가 해야 하 고 기본 네임 스페이스를 업데이트 해야 합니다.  
  
#### <a name="to-configure-the-project"></a>프로젝트를 구성 하려면  
  
1.  에 **WebPartNodeExtension** 프로젝트에서 SiteNodeExtension 및 WebPartNodeTypeProvider 명명 된 코드 파일을 두 개를 추가 합니다.  
  
2.  WebPartNodeExtension 프로젝트에 대 한 바로 가기 메뉴를 연 다음 선택 **참조 추가**합니다.  
  
3.  에 **참조 관리자-WebPartNodeExtension** 대화 상자에서 선택 하 고 **프레임 워크** 노드를 선택한 다음 선택 확인란 System.ComponentModel.Composition 및 System.Windows.Forms에 대 한 어셈블리입니다.  
  
4.  선택 된 **확장** 노드를 각 다음 어셈블리에 대 한 확인란을 선택 하 고 선택 합니다는 **확인** 단추:  
  
    -   Microsoft.SharePoint.Client  
  
    -   Microsoft.SharePoint.Client.Runtime  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  에 대 한 바로 가기 메뉴를 열고는 **WebPartNodeExtension** 프로젝트를 선택한 후 **속성**합니다.  
  
     **프로젝트 디자이너**가 열립니다.  
  
6.  **응용 프로그램** 탭을 선택합니다.  
  
7.  에 **기본 네임 스페이스** 상자 (C#) 또는 **루트 네임 스페이스** 상자 (Visual Basic)를 입력 **ServerExplorer.SharePointConnections.WebPartNode**합니다.  
  
## <a name="creating-icons-for-the-new-nodes"></a>새 노드에 대 한 아이콘 만들기  
 에 대 한 두 아이콘을 만듭니다는 **서버 탐색기** 확장: 새에 대 한 아이콘이 **웹 파트 갤러리** 노드 및 각 자식 웹 파트 노드 아래에 대 한 다른 아이콘은 **웹 파트 갤러리** 노드입니다. 이 연습의 뒷부분에서는 이러한 아이콘 노드를 연결 하는 코드를 작성 합니다.  
  
#### <a name="to-create-icons-for-the-nodes"></a>노드에 대 한 아이콘을 만들려면  
  
1.  에 **프로젝트 디자이너** WebPartNodeExtension 프로젝트에 대 한 선택은 **리소스** 탭 합니다.  
  
2.  링크 선택 **이 프로젝트는 기본 리소스 파일 포함 되어 있지 않습니다. 기본 리소스 파일을 만들려면 여기를 클릭하십시오.**를 클릭합니다.  
  
     Visual Studio 리소스 파일을 만들고 디자이너에서 열립니다.  
  
3.  디자이너의 위쪽에 있는 화살표를 선택는 **리소스 추가** 메뉴 명령을 실행 하 고 다음 선택 **새 아이콘 추가**합니다.  
  
4.  입력 **WebPartsNode** 새 아이콘에 대 한 이름을 지정 하 고 선택 합니다는 **추가** 단추입니다.  
  
     에 새로운 아이콘이 열리면는 **이미지 편집기**합니다.  
  
5.  쉽게 인식할 수 있는 디자인 있도록 16 x 16 버전의 아이콘을 편집 합니다.  
  
6.  아이콘의 32 x 32 버전에 대 한 바로 가기 메뉴를 열고 **이미지 형식 삭제**합니다.  
  
7.  3-프로젝트 자원에 두 번째 아이콘을 추가 하는 7 단계를 반복 하 고이 아이콘을 이름을 **WebPart**합니다.  
  
8.  **솔루션 탐색기**에 **리소스** 에 대 한 폴더는 **WebPartNodeExtension** 프로젝트 **WebPartsNode.ico**합니다.  
  
9. 에 **속성** 창을 열려면는 **빌드 작업** 목록에서 선택한 후 **포함 리소스**합니다.  
  
10. 에 대 한 마지막 두 단계를 반복 **WebPart.ico**합니다.  
  
## <a name="adding-the-web-part-gallery-node-to-server-explorer"></a>서버 탐색기에 웹 파트 갤러리 노드 추가  
 새 추가 하는 클래스를 만들 **웹 파트 갤러리** 노드를 각 SharePoint 사이트 노드. 클래스가 구현 하 고 새 노드를 추가 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> 인터페이스입니다. 이 인터페이스를 구현 하 여 기존 노드의 동작을 확장 하려고 할 때마다 **서버 탐색기**, 노드에 새 자식 노드를 추가 하는 등입니다.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>서버 탐색기에 웹 파트 갤러리 노드를 추가 하려면  
  
1.  다음 코드를 붙여는 **SiteNodeExtension** 코드 파일에 대 한는 **WebPartNodeExtension** 프로젝트.  
  
    > [!NOTE]  
    >  이 코드를 추가한 후 프로젝트 컴파일 오류가 발생 갖습니다. 이러한 오류는 사라집니다 이후 단계에서 코드를 추가 합니다.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="defining-a-node-type-that-represents-a-web-part"></a>웹 파트를 나타내는 노드 형식 정의  
 새로운 유형의 웹 파트를 나타내는 노드를 정의 하는 클래스를 만듭니다. Visual Studio 아래에 자식 노드를 표시 하려면이 새 노드 형식을 사용 하 여 **웹 파트 갤러리** 노드. 이러한 자식 노드의 각 SharePoint 사이트의 단일 웹 파트를 나타냅니다.  
  
 클래스가 구현 하는 새 노드 유형을 정의 하는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> 인터페이스입니다. 이 인터페이스를 구현 하는 새로운 유형의에서 노드를 정의 하려고 할 때마다 **서버 탐색기**합니다.  
  
#### <a name="to-define-the-web-part-node-type"></a>웹 파트 노드 형식을 정의 하려면  
  
1.  다음 코드를 붙여는 **WebPartNodeTypeProvider** 코드 파일에 대 한는 **WebPartNodeExtension** 프로젝트.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/webpartnodetypeprovider.cs#2)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에 대 한 모든 코드 연습에서는 **웹 파트 갤러리** 프로젝트에 노드가 포함 되었습니다. 빌드는 **WebPartNodeExtension** 프로젝트를 오류 없이 컴파일되는지 확인 합니다.  
  
#### <a name="to-build-the-project"></a>프로젝트를 빌드하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **WebPartNodeExtension** 프로젝트를 선택한 후 **빌드**합니다.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>확장 배포 하려면 VSIX 패키지 만들기  
 확장을 배포 하려면 솔루션에서 VSIX 프로젝트를 사용 하 여 VSIX 패키지를 만듭니다. 먼저 프로젝트에 포함 된 source.extension.vsixmanifest 파일을 수정 하 여 VSIX 패키지를 구성 합니다. 그런 다음 솔루션을 구축 하 여 VSIX 패키지를 만듭니다.  
  
#### <a name="to-configure-the-vsix-package"></a>VSIX 패키지를 구성 하려면  
  
1.  **솔루션 탐색기**에 **WebPartNode** 프로젝트, 열기 **source.extension.vsixmanifest** 매니페스트 편집기에서 파일입니다.  
  
     Source.extension.vsixmanifest 파일은 필요한 모든 VSIX 패키지 extension.vsixmanifest 파일의 기준이 됩니다. 이 파일에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다.  
  
2.  에 **제품 이름** 상자에 입력 **서버 탐색기에 대 한 웹 파트 갤러리 노드**합니다.  
  
3.  에 **작성자** 상자에 입력 **Contoso**합니다.  
  
4.  에 **설명** 상자에 입력 **서버 탐색기에서 SharePoint 연결 노드를 추가 하는 사용자 지정 웹 파트 갤러리 노드**합니다.  
  
5.  에 **자산** 탭 편집기의 선택은 **새로 만들기** 단추입니다.  
  
6.  에 **새 자산 추가** 대화 상자는 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
    > [!NOTE]  
    >  이 값에 해당 하는 `MefComponent` extension.vsixmanifest 파일의 요소입니다. 이 요소는 VSIX 패키지의 확장 어셈블리의 이름을 지정합니다. 자세한 내용은 참조 [MEFComponent 요소 (VSX 스키마)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551)합니다.  
  
7.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
8.  에 **프로젝트** 목록에서 선택 **WebPartNodeExtension**를 선택한 후는 **확인** 단추입니다.  
  
9. 메뉴 모음에서 **빌드**, **솔루션 빌드**, 솔루션이 오류 없이 컴파일되는지 확인 합니다.  
  
10. WebPartNode 프로젝트에 대 한 빌드 출력 폴더 WebPartNode.vsix 파일을 이제 포함 되어 있는지 확인 합니다.  
  
     빌드 출력 폴더는 기본적으로는... 프로젝트 파일에 포함 된 폴더 아래 \bin\Debug 폴더입니다.  
  
## <a name="testing-the-extension"></a>확장 테스트  
 이제 새 테스트 준비가 **웹 파트 갤러리** 노드에서 **서버 탐색기**합니다. Visual Studio의 실험적 인스턴스에서 확장 프로젝트를 디버깅 하려면 먼저 시작 합니다. 다음 새 사용 하 여 **웹 파트** Visual Studio의 실험적 인스턴스에서 노드.  
  
#### <a name="to-start-debugging-the-extension"></a>확장 프로그램 디버깅을 시작 하려면  
  
1.  관리 자격 증명으로 Visual Studio를 다시 시작을 열고는 **WebPartNode** 솔루션입니다.  
  
2.  WebPartNodeExtension 프로젝트를 열고는 **SiteNodeExtension** 코드 파일을 다음에 코드의 첫 번째 줄에 중단점을 추가 하 고는 `NodeChildrenRequested` 및 `CreateWebPartNodes` 메서드.  
  
3.  F5 키를 선택하여 디버깅을 시작합니다.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web 파트 갤러리 노드 확장을 서버 Explorer\1.0에 대 한 확장을 설치 하 고 Visual Studio의 실험적 인스턴스를 시작 합니다. Visual Studio의이 인스턴스에 있는 프로젝트 항목을 테스트 합니다.  
  
#### <a name="to-test-the-extension"></a>확장을 테스트 하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **보기**, **서버 탐색기**합니다.  
  
2.  테스트에 사용할 SharePoint 사이트 아래에 표시 되는지 확인은 **SharePoint 연결** 노드에서 **서버 탐색기**합니다. 나열 되지 않으면 다음이 단계를 따르십시오.  
  
    1.  에 대 한 바로 가기 메뉴를 열고 **SharePoint 연결**를 선택한 후 **연결 추가**합니다.  
  
    2.  에 **SharePoint 연결 추가** 대화 상자에서 다음을 선택 하 고 연결할 SharePoint 사이트에 대 한 URL을 입력에서 **확인** 단추입니다.  
  
         개발 컴퓨터에 SharePoint 사이트를 지정 하려면 입력 **http://localhost**합니다.  
  
3.  (표시 하는 사이트의 URL) 사이트 연결 노드를 확장 한 후 자식 사이트 노드를 확장 (예를 들어 **팀 사이트**).  
  
4.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `NodeChildrenRequested` 메서드를 계속 프로젝트를 디버그 하려면 F5 키를 선택 합니다.  
  
5.  Visual Studio의 실험적 인스턴스를 확장 하 고는 **웹 파트 갤러리** 노드에 있는 최상위 사이트 노드 아래에 표시 합니다.  
  
6.  Visual Studio의 다른 인스턴스에서 코드에서 이전에 설정한 중단점에서 중지 확인는 `CreateWebPartNodes` 메서드를 계속 프로젝트를 디버그 하려면 F5 키를 선택 합니다.  
  
7.  Visual Studio의 실험적 인스턴스에서 연결된 된 사이트의 모든 웹 파트에 나타나는지 확인는 **웹 파트 갤러리** 노드에서 **서버 탐색기**합니다.  
  
8.  웹 파트에 대 한 바로 가기 메뉴를 연 다음 선택 **속성**합니다.  
  
9. 에 **속성** 창에서 웹 파트에 대 한 정보가 표시 되는지 확인 합니다.  
  
10. **서버 탐색기**, 동일한 웹 파트에 대 한 바로 가기 메뉴를 열고 선택한 후 **메시지 표시**합니다.  
  
     표시 되는 메시지 상자에서 선택 된 **확인** 단추입니다.  
  
## <a name="uninstalling-the-extension-from-visual-studio"></a>Visual Studio에서 확장을 제거합니다.  
 확장 테스트를 마친 후 Visual Studio에서 제거 합니다.  
  
#### <a name="to-uninstall-the-extension"></a>확장을 제거하려면  
  
1.  메뉴 모음에서 Visual Studio의 실험적 인스턴스에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장의 목록에서 선택 **서버 탐색기에 대 한 웹 파트 갤러리 노드**를 선택한 후는 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택 된 **예** 단추입니다.  
  
4.  선택 된 **지금 다시 시작** 단추 제거를 완료 합니다.  
  
     프로젝트 항목 제거 됩니다.  
  
5.  Visual Studio (실험적 인스턴스 및 WebPartNode 솔루션 열릴 Visual Studio의 인스턴스)의 두 인스턴스를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [연습: 웹 파트를 표시 하는 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)   
 [아이콘 또는 다른 이미지 만들기 &#40;아이콘에 대 한 이미지 편집기&#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  