---
title: "Win32 오류 코드를 어디에서 찾을 수 있습니까? | Microsoft Docs"
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
  - "vc.errors"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "오류 코드, Win32"
  - "Win32, 오류 코드"
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Win32 오류 코드를 어디에서 찾을 수 있습니까?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본 시스템 설치의 INCLUDE 디렉터리에 있는 WINERROR.H에는 Win32 API 함수에 대한 오류 코드 정의가 포함되어 있습니다.  
  
 **조사식** 창이나 **간략한 조사식** 대화 상자에 코드를 입력하면 오류 코드를 찾을 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
0x80000004,hr  
```  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)