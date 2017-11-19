---
title: IDebugStackFrameSniffer::EnumStackFrames | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugStackFrameSniffer.EnumStackFrames
apilocation: jscript.dll
helpviewer_keywords: IDebugStackFrameSniffer::EnumStackFrames
ms.assetid: a7629ab3-ef7d-4bbe-a137-bb2a8ad0f384
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d64d896dcc14a280a74f64f5093b6708a7fcb5f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugstackframesnifferenumstackframes"></a>IDebugStackFrameSniffer::EnumStackFrames
현재 스레드에 대 한 스택 프레임의 열거자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumStackFrames(  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppedsf`  
 [out] 현재 스레드에 대 한 스택 프레임의 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 스택 프레임 열거자 가장 최근에 푸시된 프레임부터는 스택의 맨 위부터 프레임을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrameSniffer 인터페이스](../../winscript/reference/idebugstackframesniffer-interface.md)