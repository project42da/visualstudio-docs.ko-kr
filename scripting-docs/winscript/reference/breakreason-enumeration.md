---
title: "BREAKREASON 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: BREAKREASON
apilocation: scrobj.dll
helpviewer_keywords: 
  - "BREAKREASON 열거형"
ms.assetid: bde07ede-2f9b-4fa2-affc-f9405683f5f7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# BREAKREASON 열거형
중단 된 원인을 나타냅니다.  
  
## 구문  
  
```  
typedef enum tagBREAKREASON {  
   BREAKREASON_STEP,  
   BREAKREASON_BREAKPOINT,  
   BREAKREASON_DEBUGGER_BLOCK,  
   BREAKREASON_HOST_INITIATED,  
   BREAKREASON_LANGUAGE_INITIATED,  
   BREAKREASON_DEBUGGER_HALT,  
   BREAKREASON_ERROR,  
   BREAKREASON_JIT  
} BREAKREASON;  
```  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|BREAKREASON\_STEP|언어 엔진에서 단계별 실행 모드입니다.|  
|BREAKREASON\_BREAKPOINT|언어 엔진 명시적 중단점이 있습니다.|  
|BREAKREASON\_DEBUGGER\_BLOCK|언어 엔진 디버거 블록 다른 스레드에서 발생 합니다.|  
|BREAKREASON\_HOST\_INITIATED|호스트는 중단을 요청 했습니다.|  
|BREAKREASON\_LANGUAGE\_INITIATED|언어 엔진 브레이크를 요청 합니다.|  
|BREAKREASON\_DEBUGGER\_HALT|IDE 디버거는 중단을 요청 했습니다.|  
|BREAKREASON\_ERROR|실행 오류가 중단을 발생 합니다.|  
|BREAKREASON\_JIT|JIT 디버깅 시작에 의해 발생 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)