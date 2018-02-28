---
title: IDebugStackFrame::GetDebugProperty | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugStackFrame.GetDebugProperty
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetDebugProperty
ms.assetid: e03c7504-bce4-4a44-81e4-db8c0216538d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 898c80dc4f5ef9010db6396a78c1b17b50603dc2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugstackframegetdebugproperty"></a>IDebugStackFrame::GetDebugProperty
현재 프레임에 대 한 속성 브라우저를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDebugProperty(  
   IDebugProperty**  ppDebugProp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppDebugProp`  
 [out] 현재 프레임에 대 한 속성 브라우저입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 프레임에 대 한 속성 브라우저를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)