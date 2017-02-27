---
title: "고급 보안 설정 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.err.debug_in_zone_no_hostproc"
  - "vs.err.debug_in_zone_no_hostproc:11310"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "고급 보안 설정 대화 상자"
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 고급 보안 설정 대화 상자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 대화 상자를 사용하면 영역의 디버깅과 관련된 보안 설정을 지정할 수 있습니다.  
  
 이 대화 상자에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  **프로젝트 디자이너**가 나타나면 **보안** 탭을 클릭합니다.  **보안** 페이지에서 **ClickOnce 보안 설정 사용**, **부분 신뢰 응용 프로그램**을 차례로 선택한 다음 **고급**을 클릭합니다.  
  
## UI 요소 목록  
 **선택한 권한 집합으로 이 응용 프로그램 디버깅**  
 이 확인란을 선택하면 **보안** 페이지에서 선택한 권한 집합이 디버깅하는 동안 사용됩니다.  기본적으로 이 옵션이 선택됩니다.  
  
 보안 영역에서 디버깅을 수행하려면 **프로젝트 디자이너**의 **디버그** 페이지에 있는 **Visual Studio 호스팅 프로세스 사용** 옵션과 함께 이 옵션을 활성화해야 합니다.  
  
 WPF 웹 브라우저 응용 프로그램 프로젝트의 경우에는 **선택한 권한 집합으로 이 응용 프로그램 디버깅** 옵션이 선택된 상태로 비활성화되어 있습니다.  
  
 **원본 사이트에 응용 프로그램 액세스 허용**  
 이 확인란을 선택하면 응용 프로그램에서는 해당 응용 프로그램이 게시된 웹 사이트 또는 서버 공유에 액세스할 수 있습니다.  기본적으로 이 옵션이 선택됩니다.  
  
 **다음 URL에서 다운로드한 것처럼 이 응용 프로그램을 디버깅**  
 **게시** 페이지에서 지정한 **설치 URL**에 해당하는 웹 사이트 또는 서버 공유에 응용 프로그램이 액세스할 수 있도록 하려는 경우 여기에 해당 URL을 입력합니다.  **원본 사이트에 응용 프로그램 액세스 허용**이 선택된 경우에만 이 옵션을 사용할 수 있습니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 보안 페이지](../../ide/reference/security-page-project-designer.md)