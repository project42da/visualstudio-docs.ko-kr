---
title: "서버 탐색기를 사용하여 SharePoint 연결 찾아보기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.SharePointExplorer.SharePointConnection"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint 연결[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, SharePoint 사이트 찾아보기"
  - "Visual Studio에서 SharePoint 개발, SharePoint 연결"
ms.assetid: b3b1d97b-e990-414c-8ba5-3fd1b463fbef
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 서버 탐색기를 사용하여 SharePoint 연결 찾아보기
  이제 **서버 탐색기** 에서의 로컬 SharePoint 연결을 찾을 수 있습니다.  이 기능을 사용하면 시스템에 있는 SharePoint 사이트의 구성 요소를 탐색할 수 있습니다.  목록 정의, 콘텐츠 형식 등의 SharePoint 사이트 구성 요소가 **서버 탐색기** 의 트리 뷰에서 **SharePoint 연결** 이라는 노드에 표시됩니다.  **서버 탐색기** 를 표시하려면 메뉴 표시줄에서 **보기**, **서버 탐색기** 를 선택합니다.  SharePoint 사이트 구성 요소를 표시하는 것 외에도 바로 가기 메뉴의 명령을 사용하여 항목을 제거하거나, 속성을 보거나, 트리 뷰를 새로 고칠 수 있습니다.  
  
> [!IMPORTANT]  
>  SharePoint 사이트를 탐색하려면 SharePoint 사이트 컬렉션의 관리자여야 하고 로컬 컴퓨터 관리자 권한을 사용하여 Visual Studio를 실행해야 합니다.  그렇지 않으면 **서버 탐색기** 에 사이트가 표시되더라도 해당 노드를 확장할 수 없습니다.  사이트 컬렉션 관리자인지 아닌지 여부를 확인 하려면, 웹 브라우저를 열고 **사이트 작업** 메뉴에서 **사이트 사용 권한** 을 선택한 다음, **권한: 팀 사이트** 페이지에서 리본 메뉴의 **관리** 그룹에서 **사이트 컬렉션 관리자** 명령을 선택합니다.  사이트 컬렉션 관리자인 경우 텍스트 상자에 사용자 이름이 표시됩니다.  **사이트 컬렉션 관리자** 명령이 리본 메뉴의 관리 그룹에 표시 되지 않으면, 사용자는 사이트 컬렉션의 관리자가 아닌것이고, 사이트 관리자로 부터 사용 권한을 얻어야 합니다.  
  
## 서버 탐색기 노드  
 SharePoint 사이트의 각 구성 요소는 **서버 탐색기** 트리 뷰에서 **SharePoint 연결** 아래의 노드로 표시됩니다.  예를 들어 기본 SharePoint 사이트에는 SharePoint 사이트의 **토론** 페이지에 표시되는 토론 형식을 나타내는 토론 콘텐츠 형식이 포함되어 있습니다.  토론 콘텐츠 형식에는 여러 필드가 있습니다.  **서버 탐색기** 에서 이러한 필드를 보려면 **콘텐츠유형** 노드, **토론** 노드를 차례로 확장합니다.  이 노드 아래에는 본문, 토론 주제, 제목 등의 여러 필드 노드가 있습니다.  
  
## 노드 바로 가기 메뉴 명령  
 각 노드는 마우스 오른쪽 단추로 클릭 하거나 선택한 다음 Shift\+F10 키를 눌러 액세스할 수 있는 바로 가기 메뉴를 가집니다.  노드 명령에는 다음이 포함될 수 있습니다.  
  
|명령 이름|설명|  
|-----------|--------|  
|새로 고침|트리 뷰를 업데이트하여 마지막으로 노드를 표시한 이후 발생했을 수 있는 변경 내용을 모두 반영합니다.|  
|Delete|트리 뷰에서 선택한 노드를 제거합니다. **Note:**  **SharePoint 연결** 노드 아래에 표시된 SharePoint 연결에서만 이 명령을 사용할 수 있습니다.|  
|속성|**속성** 창에서 선택한 노드에 사용할 수 있는 속성을 표시합니다.  속성은 모두 읽기 전용이며 모든 노드에 속성이 연결되어 있는 것은 아닙니다.|  
|연결 추가|찾아보려는 SharePoint 사이트를 지정할 수 있습니다.  **SharePoint 연결** 노드 및 하위 사이트 노드에서 사용할 수 있습니다.|  
|브라우저에서 보기|선택한 목록을 웹 브라우저에 표시합니다.  이 명령은 **목록 및 라이브러리**에 포함된 **목록** 노드 아래 있는 일부 목록에 대해 사용할 수 있습니다.|  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: SharePoint 연결 추가 또는 제거](../sharepoint/how-to-add-or-remove-sharepoint-connections.md)|**서버 탐색기**의 **SharePoint 연결** 노드에 새 SharePoint 사이트를 추가하는 데 필요한 단계에 대해 설명합니다.|  
  
## 참고 항목  
 [서버 탐색기](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  