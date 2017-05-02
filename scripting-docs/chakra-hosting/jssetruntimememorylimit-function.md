---
title: "JsSetRuntimeMemoryLimit 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsSetRuntimeMemoryLimit"
helpviewer_keywords: 
  - "JsSetRuntimeMemoryLimit 함수"
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsSetRuntimeMemoryLimit 함수
런타임에 대한 현재 메모리 제한을 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### 매개 변수  
 `runtime`  
 메모리 제한을 설정할 런타임입니다.  
  
 `memoryLimit`  
 새 런타임 메모리 제한\(바이트\)을 나타내고, 메모리 제한이 없을 경우 \-1입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 메모리 제한으로 인해 제한을 초과하는 작업은 실패하고 “메모리 부족” 오류가 발생합니다.  런타임 메모리 제한을 \-1로 설정하면 런타임에 메모리 제한이 없습니다.  새 런타임은 기본적으로 메모리 제한이 없는 상태로 설정됩니다.  새 메모리 제한이 현재 사용량을 초과하면 호출에 성공하고 런타임 메모리 사용량이 제한 아래로 떨어질 때까지 이 런타임의 모든 이후 할당이 실패합니다.  
  
 런타임이 다른 스레드에서 활성인지 아닌지에 관계없이 런타임의 메모리 제한은 항상 설정할 수 있습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)