---
title: "BREAKRESUMEACTION 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- BREAKRESUMEACTION
apilocation:
- scrobj.dll
helpviewer_keywords:
- BREAKRESUMEACTION enumeration
ms.assetid: b39fcc82-7776-4caa-8155-b398de68df03
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1b830d314b1db40d7b83557d894ad6f8751bdf9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="breakresumeaction-enumeration"></a>BREAKRESUMEACTION 열거형
중단점에서 계속하는 방법을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagBREAKRESUME_ACTION {  
   BREAKRESUMEACTION_ABORT,  
   BREAKRESUMEACTION_CONTINUE,  
   BREAKRESUMEACTION_STEP_INTO,  
   BREAKRESUMEACTION_STEP_OVER,  
   BREAKRESUMEACTION_STEP_OUT,  
   BREAKRESUMEACTION_IGNORE,  
   BREAKRESUMEACTION_STEP_DOCUMENT,  
} BREAKRESUMEACTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|BREAKRESUMEACTION_ABORT|응용 프로그램을 중단합니다.|  
|BREAKRESUMEACTION_CONTINUE|실행을 계속합니다.|  
|BREAKRESUMEACTION_STEP_INTO|프로시저를 한 단계씩 실행합니다.|  
|BREAKRESUMEACTION_STEP_OVER|절차를 건너뜁니다.|  
|BREAKRESUMEACTION_STEP_OUT|현재 프로시저에서 나갑니다.|  
|BREAKRESUMEACTION_IGNORE|상태를 유지하면서 실행을 계속합니다.|  
|BREAKRESUMEACTION_STEP_DOCUMENT|다음 문서로 한 단계씩 이동합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)