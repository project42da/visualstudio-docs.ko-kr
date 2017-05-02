---
title: "ERRORRESUMEACTION 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ERRORRESUMEACTION
apilocation: scrobj.dll
helpviewer_keywords: 
  - "ERRORRESUMEACTION 열거형"
ms.assetid: a68293c8-056b-439f-83e7-69e4a38f4976
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ERRORRESUMEACTION 열거형
런타임 오류를 계속 하는 방법을 설명 합니다.  
  
## 구문  
  
```  
typedef enum tagERRORRESUMEACTION {  
   ERRORRESUMEACTION_ReexecuteErrorStatement,  
   ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller,  
   ERRORRESUMEACTION_SkipErrorStatement,  
} ERRORRESUMEACTION;  
```  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|ERRORRESUMEACTION\_ReexecuteErrorStatement|오류를 생성 하는 문을 다시 실행 합니다.|  
|ERRORRESUMEACTION\_AbortCallAndReturnErrorToCaller|언어 엔진을 오류를 처리할 수 있습니다.|  
|ERRORRESUMEACTION\_SkipErrorStatement|코드에서 오류가 발생 한 문 다음에 실행을 다시 시작 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)