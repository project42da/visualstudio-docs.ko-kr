---
title: "JsValueType 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df4f61cf9118c19a0fc35e7505af422b812d0b43
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsvaluetype-enumeration"></a>JsValueType 열거형
JsValueRef의 JavaScript 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`JsUndefined`|값은 `undefined` 값입니다.|  
|`JsNull`|값은 `null` 값입니다.|  
|`JsNumber`|이 값은 JavaScript 숫자 값입니다.|  
|`JsString`|이 값은 JavaScript 문자열 값입니다.|  
|`JsBoolean`|이 값은 JavaScript 부울 값입니다.|  
|`JsObject`|이 값은 JavaScript 개체 값입니다.|  
|`JsFunction`|이 값은 JavaScript 함수 개체 값입니다.|  
|`JsError`|이 값은 JavaScript 오류 개체 값입니다.|  
|`JsArray`|이 값은 JavaScript 배열 개체 값입니다.|  
|`JsSymbol`|이 값은 JavaScript 기호 값입니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsArrayBuffer`|이 값은 JavaScript `ArrayBuffer` 개체 값입니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsTypedArray`|이 값은 JavaScript 형식화된 배열 개체 값입니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsDataView`|이 값은 JavaScript `DataView` 개체 값입니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)