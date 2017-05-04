---
title: "JsCreateExternalArrayBuffer 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# JsCreateExternalArrayBuffer 함수
Javascript `ArrayBuffer` 개체를 만들어 외부 메모리에 액세스합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### 매개 변수  
 `data`  
 외부 메모리에 대한 포인터입니다.  
  
 `byteLength`  
 외부 메모리의 바이트 수입니다.  
  
 `finalizeCallback`  
 개체가 완료된 시기에 대한 콜백입니다. null일 수 있습니다.  
  
 `callbackState`  
 다시 finalizeCallback에 전달될 사용자가 제공한 상태입니다.  
  
 `result`  
 새로운 `ArrayBuffer` 개체입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)