---
title: "오류: 로컬 컴퓨터의 방화벽 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.firewall.localmachine"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: ab60dda9-7934-4891-aa2f-001380d2ed83
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 로컬 컴퓨터의 방화벽
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 폼을 실행하고 있는 컴퓨터인 로컬 컴퓨터의 인터넷 연결 방화벽이 원격 디버깅을 허용하도록 설정되어 있지 않습니다.  기본 전송을 사용하는 관리 또는 네이티브 원격 디버깅의 경우 DCOM 트래픽에 대해 TCP 135 포트를 열어야 합니다.  파일 및 프린터 공유가 열려 있어야 하고 devenv.exe가 예외 목록에 추가되어야 합니다.  일부 IPSEC 포트를 열어야 할 수도 있습니다.  
  
 자세한 내용은 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하십시오.