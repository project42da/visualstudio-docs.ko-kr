---
title: "JsSetRuntimeBeforeCollectCallback 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsSetRuntimeBeforeCollectCallback"
helpviewer_keywords: 
  - "JsSetRuntimeBeforeCollectCallback 함수"
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsSetRuntimeBeforeCollectCallback 함수
가비지 수집 전에 런타임에서 호출되는 콜백 함수를 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### 매개 변수  
 `runtime`  
 할당 콜백을 등록할 런타임입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
 `beforeCollectCallback`  
 설정되는 콜백 함수입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 콜백은 현재 런타임 스레드에서 호출되므로 콜백이 완료될 때까지 실행이 차단됩니다.  
  
 콜백은 호스트에서 가비지 수집을 준비하는 데 사용됩니다.  예를 들어 불필요한 참조 및 Chakra 개체를 해제합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)