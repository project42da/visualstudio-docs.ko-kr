---
title: "JsDoubleToNumber 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsDoubleToNumber"
helpviewer_keywords: 
  - "JsDoubleToNumber 함수"
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsDoubleToNumber 함수
`double` 값에서 숫자 값을 만듭니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### 매개 변수  
 `doubleValue`  
 숫자 값으로 변환할 `double`입니다.  
  
 `value`  
 새 숫자 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)