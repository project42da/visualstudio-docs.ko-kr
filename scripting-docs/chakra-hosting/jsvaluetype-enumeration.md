---
title: "JsValueType 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsValueType"
helpviewer_keywords: 
  - "JsValueType 열거형"
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# JsValueType 열거형
JsValueRef의 JavaScript 형식입니다.  
  
## 구문  
  
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
  
## 멤버  
  
### 값  
  
|이름|설명|  
|--------|--------|  
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
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)