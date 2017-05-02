---
title: "JsDisposeRuntime 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsDisposeRuntime"
helpviewer_keywords: 
  - "JsDisposeRuntime 함수"
ms.assetid: 0aefde3f-7250-48be-afc5-53ea85c12f30
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsDisposeRuntime 함수
런타임을 삭제합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsDisposeRuntime(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 매개 변수  
 `runtime`  
 삭제할 런타임입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 런타임이 삭제된 후 모든 런타임이 소유한 모든 리소스는 무효화되고 사용할 수 없습니다.  런타임이 활성화되면\(즉, 특정 스레드에서 최신 상태로 설정됨\)  런타임을 삭제할 수 없습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)