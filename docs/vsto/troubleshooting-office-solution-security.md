---
title: "Office 솔루션 보안 문제 해결 | Microsoft Docs"
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
  - "보안[Visual Studio에서 Office 개발], 문제 해결"
ms.assetid: 6f85dd61-31f5-47da-8409-21ad827eb2dd
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# Office 솔루션 보안 문제 해결
  이 항목에서는 Office 솔루션의 보안을 설정할 때 발생할 수 있는 일반적인 문제를 해결하기 위한 팁을 제공합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 제한된 사이트에서 신뢰할 수 있는 솔루션을 설치할 수 없다.  
 사용자가 웹 사이트의 Internet Explorer 제한 된 사이트 영역에 나열 되어 있는 경우 솔루션이 웹 위치에서 설치할 수 없습니다.  이는 솔루션이 신뢰할 수 있는 인증서로 서명된 경우에도 해당됩니다.  
  
 배포 매니페스트의 URL은 다음 다섯 개의 영역 중 하나로 분류할 수 있습니다.  
  
-   내 컴퓨터  
  
-   Internet  
  
-   로컬 인트라넷  
  
-   신뢰할 수 있는 사이트  
  
-   제한된 사이트  
  
 배포 매니페스트의 위치가 제한된 사이트 영역에 할당된 경우에는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 솔루션을 설치할 수 없습니다.  위치를 알고 있으며 신뢰할 수 있으면 제한된 사이트 영역에서 해당 위치를 제거하고 솔루션을 설치할 수 있습니다.  영역을 관리하는 방법에 대한 자세한 내용은 [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774)를 참조하십시오.  
  
## Internet Explorer 보안 강화 구성 또는 Internet Explorer 7이 설치된 경우 네트워크 파일 공유나 웹 위치에서 솔루션을 설치할 수 없다.  
 Internet Explorer 향상 된 보안 구성 \(IEESC\) 및 Windows Server 2003에서 및 Internet Explorer 7 이상은 사용자가 인터넷을 찾아볼 수 현저 하 게 제한 합니다.  사용자가 네트워크 파일 공유 또는 웹 위치에서 Office 솔루션을 설치 하려고 하면 다음 오류 메시지가 나타날 수 있습니다: "에 대 한 배포 매니페스트를 서명 하는 인증서를 사용 하기 때문에이 응용 프로그램에서 사용자 지정 기능이 작동 하지 않습니다  *SolutionName* 트러스트 되지 않습니다.  도움이 필요하면 관리자에게 문의하십시오."라는 오류 메시지가 나타날 수 있습니다.  
  
 IEESC 및 Internet Explorer 7 이상은 배포 매니페스트의 URL이 인터넷 영역에 분류 된 매니페스트 신뢰할 수 있는 게시자의 인증서가 있어야 또는 솔루션을 설치할 수 없습니다.  IEESC가 설치되어 있지 않은 경우에는 기본적으로 신뢰 여부를 결정하라는 메시지가 최종 사용자에게 표시됩니다.  
  
 IEESC 및 Internet Explorer 7 효과 관리 하 고 이상 웹 사이트 및 범용 명명 규칙 \(UNC\) 경로 확인 하려면 신뢰 하 고 신뢰할 수 있는 보안 영역 \(로컬 인트라넷 또는 신뢰할 수 있는 사이트\) 중 하나를 추가 합니다.영역을 관리 하는 방법에 대 한 내용은 [ClickOnce 신뢰할 수 있는 게시자 구성](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  