---
title: "JsSetIndexedProperty 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsSetIndexedProperty"
helpviewer_keywords: 
  - "JsSetIndexedProperty 함수"
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsSetIndexedProperty 함수
개체의 지정된 인덱스에서 값을 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### 매개 변수  
 `object`  
 작동할 개체입니다.  
  
 `index`  
 설정할 인덱스입니다.  
  
 `value`  
 설정할 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)