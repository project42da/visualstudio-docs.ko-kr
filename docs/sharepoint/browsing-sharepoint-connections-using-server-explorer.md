---
title: "서버 탐색기를 사용 하 여 SharePoint 연결 찾아보기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.SharePointExplorer.SharePointConnection
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, browsing SharePoint sites
- SharePoint development in Visual Studio, SharePoint Connections
- SharePoint Connections [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5ea474f2439b6da519563f08ffe4ddc2f6dcef30
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="browsing-sharepoint-connections-using-server-explorer"></a>서버 탐색기를 사용하여 SharePoint 연결 찾아보기
  로컬 SharePoint 연결에서 검색할 수 있습니다 **서버 탐색기**합니다. 이 방법을 사용하면 시스템에서 SharePoint 사이트의 구성 요소를 탐색할 수 있습니다. SharePoint 사이트 구성 요소 목록 정의 콘텐츠 형식 등 명명 된 노드에 표시 **SharePoint 연결** 의 트리 보기에서 **서버 탐색기**합니다. 표시 하려면 **서버 탐색기**, 메뉴 모음에서 **보기**, **서버 탐색기**합니다. SharePoint 사이트 구성 요소를 표시하는 것 외에도 바로 가기 메뉴의 명령을 사용하여 항목을 제거하거나, 속성을 보거나, 트리 뷰를 새로 고칠 수 있습니다.  
  
> [!IMPORTANT]  
>  SharePoint 사이트를 탐색하려면 SharePoint 사이트 컬렉션의 관리자여야 하고 로컬 컴퓨터의 관리자로서 Visual Studio를 실행해야 합니다. 사이트에 표시 되는 그렇지 않은 경우 **서버 탐색기**, 해당 노드를 확장할 수 없습니다. 사이트 컬렉션의 관리자 인 여부를 확인 하려면 웹 브라우저를 열고에서 사이트를 엽니다는 **사이트 작업** 메뉴 선택 **사이트 사용 권한**를 선택한 후의 **사용 권한: 팀 사이트** 페이지를 선택 합니다는 **사이트 모음 관리자** 명령을 **관리** 리본 메뉴에 그룹화 합니다. 사이트 모음 관리자 사용자 이름 텍스트 상자에 나타납니다. 경우는 **사이트 모음 관리자** 명령이 리본 메뉴에서 관리 그룹에 표시 되지 않으면 사이트 컬렉션의 관리자가 아니라면 하 고 사이트 관리자에 게 적절 한 사용 권한을 얻어야 합니다.  
  
## <a name="server-explorer-nodes"></a>서버 탐색기 노드  
 SharePoint 사이트의 모든 구성 요소에서 노드로 표시 되는 **서버 탐색기** 트리 보기에서 **SharePoint 연결**합니다. 기본 SharePoint 사이트 콘텐츠 형식을 토론 형식에 표시 되는 토론 호출을 포함 하는 예를 들어는 **토론** SharePoint 사이트의 페이지입니다. 토론 콘텐츠 형식에는 여러 필드가 포함 되어 있습니다. 이러한 필드를 보려면 **서버 탐색기**를 확장 하 고는 **콘텐츠 형식** 노드를 차례로 **토론** 노드. 아래에서 본문, 토론 주제 및 Title과 같은 몇 가지 field 노드를 됩니다.  
  
## <a name="node-shortcut-menu-commands"></a>노드 바로 가기 메뉴 명령  
 각 노드에는 노드를 마우스 오른쪽 단추로 클릭하거나 노드를 선택한 다음 Shift+F10 키를 선택하여 액세스하는 바로 가기 메뉴가 있습니다. 노드 명령에는 다음과 같습니다.  
  
|명령 이름|설명|  
|------------------|-----------------|  
|새로 고침|트리 뷰에서 노드를 표시 된 마지막 시간 이후 발생 했을 수 있는 모든 변경 내용을 반영 하도록 업데이트 합니다.|  
|삭제|트리 뷰에서 선택 된 노드를 제거합니다. **참고:** 이 명령을 나열 하는 SharePoint 연결에 대해서만 사용할 수는 **SharePoint 연결** 노드.|  
|속성|선택 된 노드에 대해 사용할 수 있는 속성이 표시 됩니다는 **속성** 창. 속성은 모두 읽기 전용 및 일부 노드에 연관 된 속성입니다.|  
|연결 추가|탐색 하려면 SharePoint 사이트를 지정할 수 있습니다. 사용할 수는 **SharePoint 연결** 노드 및 하위 사이트 노드.|  
|브라우저에서 보기|웹 브라우저에서 선택한 목록을 표시합니다. 이 명령은 아래에 몇 가지 목록에서 사용할 수는 **나열** 에 포함 되어 있는 노드 **목록 및 라이브러리**합니다.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: SharePoint 연결 추가 또는 제거](../sharepoint/how-to-add-or-remove-sharepoint-connections.md)|새 SharePoint 사이트를 추가 하는 데 필요한 단계를 설명는 **SharePoint 연결** 노드에서 **서버 탐색기**합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  