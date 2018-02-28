---
title: IDebugCodeContext::SetBreakPoint | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugCodeContext.SetBreakPoint
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::SetBreakPoint
ms.assetid: ecd42eae-66fa-40d3-9e47-08b826784108
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a0111deba23f29aa6b7d31a1aed8d729ff4e7fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugcodecontextsetbreakpoint"></a>IDebugCodeContext::SetBreakPoint
설정 하거나이 코드 컨텍스트에 중단점을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetBreakPoint(  
   BREAKPOINT_STATE  bps  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bps`  
 [in] 이 코드 컨텍스트에 대 한 중단점 상태를 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드를 설정 하거나 여기서 코드에 중단점을 해제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCodeContext 인터페이스](../../winscript/reference/idebugcodecontext-interface.md)   
 [BREAKPOINT_STATE 열거형](../../winscript/reference/breakpoint-state-enumeration.md)