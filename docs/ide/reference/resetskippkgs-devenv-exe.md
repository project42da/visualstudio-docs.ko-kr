---
title: "/ResetSkipPkgs(devenv.exe) | Microsoft Docs"
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
  - "/ResetSkipPkgs 스위치"
  - "Devenv, /ResetSkipPkgs 스위치"
  - "ResetSkipPkgs 스위치"
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: 3
caps.handback.revision: 3
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /ResetSkipPkgs(devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

문제 있는 VSPackages가 로드되지 않도록 사용자가 VSPackages에 추가한 로딩 건너뛰기 옵션을 모두 지운 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
## 구문  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## 설명  
 SkipLoading 태그가 있으면 VSPakage 로딩이 비활성화됩니다. 태그를 지우면 VSPackage 로딩이 다시 활성화됩니다.  
  
## 예제  
 다음 예제에서는 모든 SkipLoading 태그를 지웁니다.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)