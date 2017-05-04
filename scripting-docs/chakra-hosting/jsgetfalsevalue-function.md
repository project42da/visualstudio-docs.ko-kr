---
title: "JsGetFalseValue 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetFalseValue"
helpviewer_keywords: 
  - "JsGetFalseValue 함수"
ms.assetid: 621a584c-4ca8-4ba0-b19a-6cb50cf830b6
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsGetFalseValue 함수
현재 스크립트 컨텍스트에서 `false` 값을 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetFalseValue(  
   _Out_ JsValueRef *falseValue  
);  
```  
  
#### 매개 변수  
 `falseValue`  
 `false` 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)