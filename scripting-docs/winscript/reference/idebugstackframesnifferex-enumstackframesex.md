---
title: IDebugStackFrameSnifferEx::EnumStackFramesEx | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugStackFrameSnifferEx.EnumStackFramesEx
apilocation: jscript.dll
helpviewer_keywords: IDebugStackFrameSnifferEx::EnumStackFramesEx
ms.assetid: b656b581-aff0-4984-8d8a-a1c7a8e6558a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a96a382c1dce73731fdd4326d8b0d1c35b7aa33
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugstackframesnifferexenumstackframesex"></a>IDebugStackFrameSnifferEx::EnumStackFramesEx
현재 스레드에 대 한 스택 프레임의 열거자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumStackFramesEx(  
   DWORD_PTR                dwSpMin,  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSpMin`  
 [in] 스택 프레임을 열거 하기 위한 낮은 주소 제한입니다.  
  
 `ppedsf`  
 [out] 현재 스레드에 대 한 스택 프레임의 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 스택 프레임 열거자는 스택의 가장 최근에 푸시된 프레임의 위쪽부터 시작 하는 프레임을 반환 합니다. 보다 크거나 같은 경우에 주소와만 스택 프레임을 포함 하는 열거자 `dwSpMin`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrameSnifferEx 인터페이스](../../winscript/reference/idebugstackframesnifferex-interface.md)