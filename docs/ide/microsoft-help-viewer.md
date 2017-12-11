---
title: "Visual Studio 오프라인 도움말 설명서 | Microsoft Docs"
ms.custom: 
ms.date: 11/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: hv_general
helpviewer_keywords:
- Microsoft Help Viewer Help
- Help Viewer, printing a topic
- printing a topic [Help Viewer]
- Help Viewer, toolbar
- Help on Help [Help Viewer]
- Help Viewer, window components
- Help Viewer, navigating
- toolbar [Help Viewer]
ms.assetid: 74e41666-2ce8-4ac0-a0e5-3723d1e322c2
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d770c1b7d05117243643680898348b71cf0a978d
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="microsoft-help-viewer"></a>Microsoft 도움말 뷰어
Microsoft 도움말 뷰어를 사용하여 Visual Studio, .NET Framework, 언어 참조, SQL Server 및 Windows Development를 포함해 로컬 컴퓨터에서 다양한 제품 및 기술에 대한 콘텐츠를 설치하고 볼 수 있습니다. 도움말 뷰어를 통해 다음을 수행할 수 있습니다.  

-   책이라고도 하는 콘텐츠의 집합을 찾고 다운로드합니다.  

-   목차를 찾아보고 검색하여 제목으로 항목을 찾습니다.  

-   색인에서 주제를 조회합니다.  

-   전체 텍스트 검색을 사용하여 정보를 찾습니다.  

-   항목을 보고 책갈피를 설정하고 인쇄합니다.

도움말 뷰어를 설치하려면 [Microsoft 도움말 뷰어 설치](../ide/microsoft-help-viewer-installation.md)를 참조하세요. 온라인 대신 도움말 뷰어에서 도움말 항목을 읽기 시작하려면 Visual Studio에서 **도움말** 메뉴로 이동하고 **도움말 기본 설정 지정**, **도움말 뷰어에서 시작**을 차례로 선택합니다.

## <a name="help-viewer-tour"></a>도움말 뷰어 둘러보기
탐색 탭을 사용하여 설치된 콘텐츠에서 정보를 찾고, 항목 탭에서 설치된 콘텐츠를 보고, **콘텐츠 관리** 탭을 사용하여 콘텐츠를 관리할 수 있습니다. 도구 모음에서 단추를 사용하여 추가 작업을 수행하고 창의 오른쪽 아래에서 추가 정보를 찾을 수도 있습니다.

### <a name="navigation-tabs"></a>탐색 탭

|탭|설명|
|---|-----------|
|목차|설치된 콘텐츠를 계층 구조로 표시(목차) 조건을 지정하여 나타나는 제목을 필터링할 수 있습니다.|
|인덱스|인덱싱된 용어를 사전순으로 표시합니다. 인덱스를 검색하고 조건을 지정하여 항목을 필터링할 수 있으며 인덱스 항목이 지정한 텍스트를 포함하거나 지정한 텍스트로 시작하게 할 수 있습니다.|
|즐겨찾기|**즐겨찾기에 추가** 단추를 선택하여 항목을 “즐겨찾기”로 지정하면 해당 항목이 이 탭에 나타납니다. 기록 섹션에는 최근에 본 항목의 목록이 표시됩니다.|
|검색|코드 및 항목 제목을 비롯하여 콘텐츠 어디에나 있는 어구를 검색할 수 있는 텍스트 상자를 제공합니다.|

### <a name="viewing-topics"></a>항목 보기
각 항목이 해당하는 탭에 나타나며 동시에 여러 항목을 열 수 있습니다.

### <a name="managing-content"></a>콘텐츠 관리
**콘텐츠 관리** 탭을 사용하여 콘텐츠를 설치, 업데이트, 이동 및 삭제할 수 있습니다. 탭의 위쪽에서 **설치 소스** 컨트롤을 사용하여 네트워크 위치에서 책을 설치할지 아니면 디스크나 URI에서 책을 설치할지를 지정할 수 있습니다. **로컬 저장소 경로** 상자에는 로컬 컴퓨터에서 책이 설치된 위치가 표시되며, **이동** 단추를 선택하여 책을 다른 위치로 이동할 수 있습니다.

콘텐츠 목록에는 설치할 수 있거나 이미 설치한 책, 업데이트를 사용할 수 있는지 여부 및 각 책의 크기가 표시됩니다. 적절한 **추가** 또는 **제거** 링크를 선택한 다음 **보류 중인 변경 내용** 창에서 **업데이트** 단추를 선택하여 하나 이상의 책을 설치하거나 제거할 수 있습니다. 이미 설치한 책에 대한 업데이트를 사용할 수 있는 경우 창의 아래쪽에서 **지금 다운로드하려면 여기를 클릭하세요.** 링크를 선택하여 해당 콘텐츠를 새로 고칠 수 있습니다. 또한 추가 책을 설치할 때 업데이트를 사용할 수 있는 경우 모든 설치된 책이 새로 고쳐집니다.

**참고:** **콘텐츠 관리** 탭의 기능은 도움말 뷰어 관리자가 해당하는 기능을 비활성화하거나 인터넷에 액세스할 수 없는 경우 달라질 수 있습니다.

### <a name="toolbar-buttons"></a>도구 모음 단추
도움말 뷰어 창의 도구 모음에 포함되어 있는 단추는 다음과 같습니다.  

-   **콘텐츠에 항목 표시** 단추는 **콘텐츠** 탭에서 항목 위치를 보여 줍니다.  

-   **즐겨찾기에 추가** 단추는 활성 항목을 **즐겨찾기** 탭에 추가합니다.  

-   **항목에서 찾기** 단추는 활성 항목에서 검색 텍스트를 강조 표시합니다.  

-   **인쇄** 단추는 활성 항목의 미리 보기를 인쇄하거나 표시합니다.  

-   **뷰어 옵션** 단추는 나타나는 텍스트의 크기, 반환할 검색 결과의 수, 기록에 표시할 항목의 수 및 온라인으로 업데이트를 확인할지 여부 등의 설정을 표시합니다.  

-   **콘텐츠 관리** 단추는 **콘텐츠 관리** 탭을 활성화합니다.  

-   오른쪽의 작은 삼각형은 항목 탭 및 **콘텐츠 관리** 탭을 비롯한 탭의 목록을 엽니다. 활성 탭으로 만들 탭 이름을 선택할 수 있습니다. 

## <a name="see-also"></a>참고 항목
[Microsoft 도움말 뷰어 설치](../ide/microsoft-help-viewer-installation.md)  
[도움말 뷰어 관리자 가이드](../ide/help-viewer-administrator-guide.md)  
[로컬 콘텐츠 설치 및 관리](../ide/install-and-manage-local-content.md)
