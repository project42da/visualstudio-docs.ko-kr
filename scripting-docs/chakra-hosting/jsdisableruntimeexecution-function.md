---
title: "JsDisableRuntimeExecution 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsDisableRuntimeExecution"
helpviewer_keywords: 
  - "JsDisableRuntimeExecution 함수"
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsDisableRuntimeExecution 함수
스크립트 실행을 일시 중단하고 런타임에 실행 중인 모든 스크립트를 종료합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 매개 변수  
 `runtime`  
 일시 중단할 런타임입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 일시 중단된 런타임에 대한 호출은 `JsEnableRuntimeExecution`이 호출될 때까지 실패합니다.  
  
 이 API는 런타임이 활성화된 스레드에서 호출할 필요가 없습니다.  런타임이 일시 중단 상태로 설정되더라도 실행 중인 스크립트가 즉시 일시 중단되지 않을 수 있습니다. 실행 중인 스크립트는 catch할 수 없는 예외와 함께 최대한 빨리 종료됩니다.  
  
 이미 일시 중단된 실행을 런타임에 일시 중단할 수는 없습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)