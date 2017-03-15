---
title: "/LCID (devenv.exe) | Microsoft Docs"
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
  - "/l Devenv 스위치"
  - "/lcid Devenv 스위치"
  - "Devenv, /LCID 스위치"
  - "언어 기본값"
  - "LCID devenv 스위치"
  - "로캘 ID"
  - "로캘 ID, IDE 설정"
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /LCID (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE\(통합 개발 환경\) 내에서 텍스트, 통화 및 다른 값에 사용되는 기본 언어를 설정합니다.  
  
## 구문  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## 인수  
 `LocaleID`  
 필수 요소.  지정된 언어의 LCID\(로캘 ID\)입니다.  
  
## 설명  
 IDE를 로드하여 환경에 대한 기본 자연 언어를 설정합니다.  이 변경 내용은 세션 간에 유지되며 IDE의 **옵션** 대화 상자에 있는 **환경** 옵션의 **국가별 설정** 창에 반영됩니다.  
  
 지정한 언어를 사용할 수 없는 경우 \/LCID 스위치가 무시됩니다.  
  
 다음 표에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 지원하는 언어의 LCID 목록을 보여 줍니다.  
  
|Language|LCID|  
|--------------|----------|  
|중국어\(간체\)|2052|  
|중국어\(번체\)|1028|  
|영어|1033|  
|프랑스어|1036|  
|독일어|1031|  
|이탈리아어|1040|  
|일본어|1041|  
|한국어|1042|  
|스페인어|3082|  
  
## 예제  
 다음 예제에서는 영어 리소스 문자열을 사용하는 IDE를 로드합니다.  
  
```  
devenv /LCID 1033  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [옵션 대화 상자, 환경, 국가별 설정](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)