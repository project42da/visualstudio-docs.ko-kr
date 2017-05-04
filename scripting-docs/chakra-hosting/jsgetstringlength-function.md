---
title: "JsGetStringLength 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetStringLength"
helpviewer_keywords: 
  - "JsGetStringLength 함수"
ms.assetid: e9f9f28c-e644-439c-aee5-7ce362f71347
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsGetStringLength 함수
문자열 값의 길이를 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetStringLength(  
   _In_ JsValueRef stringValue,  
   _Out_ int *length  
);  
```  
  
#### 매개 변수  
 `stringValue`  
 길이를 가져올 문자열 값입니다.  
  
 `length`  
 문자열의 길이입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)