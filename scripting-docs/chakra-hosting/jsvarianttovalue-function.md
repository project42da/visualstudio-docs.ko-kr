---
title: "JsVariantToValue 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsVariantToValue"
helpviewer_keywords: 
  - "JsVariantToValue 함수"
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsVariantToValue 함수
전달된 `VARIANT`의 프로젝션인 JavaScript 값을 생성합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### 매개 변수  
 `variant`  
 프로젝션해야 하는 `VARIANT`입니다.  
  
 `value`  
 `VARIANT`의 프로젝션인 JavaScript 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 프로젝션된 값은 스크립트에서 COM 자동화 개체를 호출하는 데 스크립트가 사용할 수 있습니다.  호스트는 COM 스레딩 규칙 적용을 담당합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)