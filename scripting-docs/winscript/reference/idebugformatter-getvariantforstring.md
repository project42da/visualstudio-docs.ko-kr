---
title: IDebugFormatter::GetVariantForString | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugFormatter.GetVariantForString
apilocation: jscript.dll
helpviewer_keywords: IDebugFormatter::GetVariantForString
ms.assetid: 2993431d-0ee2-4d8d-b62c-0a810a8bc391
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f9f783c8fe1864999e017ff348853df5464c93f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugformattergetvariantforstring"></a>IDebugFormatter::GetVariantForString
지정된 된 문자열을 포함 하는 VARIANT를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVariantForString(  
   LPCOLESTR  pwstrValue,  
   VARIANT*   pvar  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwstrValue`  
 [in] VARIANT에 저장 하는 문자열입니다.  
  
 `pvar`  
 [out] VARIANT 포함 된 `pwstrValue`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정된 된 문자열을 포함 하는 VARIANT를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFormatter 인터페이스](../../winscript/reference/idebugformatter-interface.md)