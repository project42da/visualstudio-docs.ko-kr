---
title: "도움말 뷰어 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도움말 뷰어 2.0, 문제 해결"
  - "문제 해결[도움말 뷰어 2.0]"
ms.assetid: 461a4553-064a-4142-a2d2-058658b9ba12
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 도움말 뷰어 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목은 도움말 뷰어에서 발생할 수 있는 문제에 대해 설명합니다.  
  
## 오디오가 작동하지 않습니다.  
 도움말 뷰어에는 오디오 플레이어가 포함되지 않습니다.  오디오가 포함된 콘텐츠를 다운로드할 때 **재생**을 선택해도 아무 반응이 없을 경우 오디오 플레이어를 설치한다.  
  
## Windows Server 2008, Windows Server 2008 with SP1 또는 Windows Server 2008 R2에서는 검색이 작동하지 않습니다.  
 도움말 뷰어에서 검색 및 필터링 기능을 사용하려면 Windows 검색 서비스를 설치하고 활성화해야 합니다.  기본적으로 Windows Server 2008, Windows Server 2008 서비스 팩 1\(SP1\) 및 Windows Server 2008 R2에서는 이 서비스가 해제되어 있습니다.  
  
#### Windows 검색 서비스를 활성화하려면  
  
1.  서버 관리자를 시작합니다.  
  
2.  왼쪽 탐색 창에서 **역할**을 선택합니다.  
  
3.  역할 요약 창에서 **역할 추가**를 선택합니다.  
  
4.  파일 서비스 역할을 선택한 후 **다음** 단추를 선택합니다.  
  
5.  Windows 검색 역할 서비스를 선택합니다.  
  
## 추가 리소스  
 다음 리소스를 사용하여 도움말 뷰어에 대한 자세한 정보를 확인하고 피드백을 제공할 수 있습니다.  
  
-   피드백을 제공하려면 Microsoft 웹사이트의 [Microsoft Connect](http://go.microsoft.com/fwlink/?linkid=243983)를 참조하거나 [hlpfdbk@microsoft.com](mailto:hlpfdbk@microsoft.com)으로 전자 메일을 보내십시오.  
  
-   자세한 내용은 [Developer Documentation and Help System](http://go.microsoft.com/fwlink/?LinkId=232741) 포럼 및 [The Help Guy](http://go.microsoft.com/fwlink/?LinkId=232743) 블로그를 참조하십시오.  
  
## 참고 항목  
 [도움말 뷰어 2.1 관리자 가이드](http://go.microsoft.com/fwlink/?LinkId=243985)