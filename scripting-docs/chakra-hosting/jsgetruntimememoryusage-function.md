---
title: "JsGetRuntimeMemoryUsage 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetRuntimeMemoryUsage"
helpviewer_keywords: 
  - "JsGetRuntimeMemoryUsage 함수"
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsGetRuntimeMemoryUsage 함수
런타임에 대한 현재 메모리 사용량을 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### 매개 변수  
 `runtime`  
 메모리 사용량을 검색할 런타임입니다.  
  
 `memoryUsage`  
 런타임의 현재 메모리 사용량\(바이트\)입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 런타임이 다른 스레드에서 활성인지 아닌지에 관계없이 메모리 사용량은 항상 검색할 수 있습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)