---
title: "JsGetCurrentContext 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetCurrentContext"
helpviewer_keywords: 
  - "JsGetCurrentContext 함수"
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsGetCurrentContext 함수
스레드에서 현재 스크립트 컨텍스트를 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### 매개 변수  
 `currentContext`  
 스레드의 현재 스크립트 컨텍스트이고, 현재 스크립트 컨텍스트가 없으면 null입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)