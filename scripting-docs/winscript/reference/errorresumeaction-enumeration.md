---
title: "ERRORRESUMEACTION 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ERRORRESUMEACTION
apilocation: scrobj.dll
helpviewer_keywords: ERRORRESUMEACTION enumeration
ms.assetid: a68293c8-056b-439f-83e7-69e4a38f4976
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 914c1d7aa4d2935ea94322ebd257f4135d79e9c0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="errorresumeaction-enumeration"></a>ERRORRESUMEACTION 열거형
런타임 오류에서 계속 진행하는 방법을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagERRORRESUMEACTION {  
   ERRORRESUMEACTION_ReexecuteErrorStatement,  
   ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller,  
   ERRORRESUMEACTION_SkipErrorStatement,  
} ERRORRESUMEACTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|ERRORRESUMEACTION_ReexecuteErrorStatement|오류를 생성 하는 문을 다시 실행 합니다.|  
|ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller|언어 엔진을 오류를 처리할 수 있습니다.|  
|ERRORRESUMEACTION_SkipErrorStatement|문 다음에 오류를 생성 하는 코드의 실행을 다시 시작 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)