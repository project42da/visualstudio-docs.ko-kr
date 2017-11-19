---
title: "SCRIPTTHREADSTATE 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SCRIPTTHREADSTATE
apilocation: scrobj.dll
helpviewer_keywords: SCRIPTTHREADSTATE enum
ms.assetid: 975ec66b-c095-40ac-8ba9-631adb97b589
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e18cc6f5f2afb1dcea6835983f69f6a6f7b9280
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptthreadstate-enumeration"></a>SCRIPTTHREADSTATE 열거형
스크립팅 엔진의 스레드 상태를 지정합니다. 이 열거형은에서 사용 된 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagSCRIPTTHREADSTATE {  
    SCRIPTTHREADSTATE_NOTINSCRIPT  = 0,  
    SCRIPTTHREADSTATE_RUNNING      = 1  
} SCRIPTTHREADSTATE;  
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTTHREADSTATE_NOTINSCRIPT|지정 된 스레드 스크립팅된 이벤트를 즉시 실행 하는 처리 스크립트 텍스트를 처리 또는 스크립트 매크로 실행 합니다. 현재는 아님.|  
|SCRIPTTHREADSTATE_RUNNING|지정 된 스레드 스크립팅된 이벤트를 즉시 실행 하는 처리 스크립트 텍스트를 처리 또는 스크립트 매크로 실행 적극적으로.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)