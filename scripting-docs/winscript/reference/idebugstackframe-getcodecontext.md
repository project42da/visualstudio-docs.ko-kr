---
title: IDebugStackFrame::GetCodeContext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugStackFrame.GetCodeContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetCodeContext
ms.assetid: 3dd378f3-e4b7-413e-8812-0f6c72952544
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b872e63169f6c2d70cd3476324b3d0071718350
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugstackframegetcodecontext"></a>IDebugStackFrame::GetCodeContext
스택 프레임을 연관 된 현재 코드 컨텍스트를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCodeContext(  
   IDebugCodeContext**  ppcc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppcc`  
 [out] 스택 프레임와 관련 된 코드 컨텍스트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 스택 프레임을 연관 된 현재 코드 컨텍스트를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)