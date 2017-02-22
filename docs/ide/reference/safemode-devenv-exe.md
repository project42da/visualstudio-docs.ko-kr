---
title: "/SafeMode(devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/SafeMode Devenv 스위치"
  - "Devenv, /SafeMode 스위치"
  - "SafeMode 스위치"
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /SafeMode(devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기본 환경과 서비스만 로드하는 안전 모드에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
## 구문  
  
```  
devenv /SafeMode   
```  
  
## 설명  
 이 스위치는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 시작될 때 모든 타사 VSPackages가 로드되지 않도록 하여 안정적으로 실행되도록 합니다.  
  
## 설명  
 다음 예제에서는 안전 모드에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
## 코드  
  
```  
Devenv.exe /SafeMode  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)