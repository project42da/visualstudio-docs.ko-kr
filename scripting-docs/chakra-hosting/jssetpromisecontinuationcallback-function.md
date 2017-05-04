---
title: "JsSetPromiseContinuationCallback 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# JsSetPromiseContinuationCallback 함수
나중에 실행하기 위해 작업을 큐에 추가해야 하는 경우 컨텍스트에서 호출되는 프라미스 연속 콜백 함수를 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### 매개 변수  
 `promiseContinuationCallback`  
 설정되는 콜백 함수입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)