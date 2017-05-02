---
title: "JsValueToVariant 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsValueToVariant"
helpviewer_keywords: 
  - "JsValueToVariant 함수"
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsValueToVariant 함수
전달된 `VARIANT`를 JavaScript 값의 프로젝션으로 초기화합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### 매개 변수  
 `object`  
 `VARIANT`로 프로젝트할 JavaScript 값입니다.  
  
 `variant`  
 프로젝션으로 초기화될 `VARIANT` 구조체에 대한 포인터입니다.  
  
## 반환 값  
  
## 설명  
 프로젝션 `VARIANT`는 COM 자동화 클라이언트에서 프로젝션된 JavaScript 개체를 호출하는 데 사용할 수 있습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)