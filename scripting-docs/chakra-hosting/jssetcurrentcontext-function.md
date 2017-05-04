---
title: "JsSetCurrentContext 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsSetCurrentContext"
helpviewer_keywords: 
  - "JsSetCurrentContext 함수"
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsSetCurrentContext 함수
스레드에서 현재 스크립트 컨텍스트를 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### 매개 변수  
 `context`  
 현재로 설정할 스크립트 컨텍스트입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)