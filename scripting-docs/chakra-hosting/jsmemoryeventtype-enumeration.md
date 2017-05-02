---
title: "JsMemoryEventType 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsMemoryEventType"
helpviewer_keywords: 
  - "JsMemoryEventType 열거형"
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsMemoryEventType 열거형
할당 콜백 이벤트 형식입니다.  
  
## 구문  
  
```  
enum JsMemoryEventType;  
```  
  
## 멤버  
  
### 값  
  
|이름|설명|  
|--------|--------|  
|`JsMemoryAllocate`|메모리 할당에 대한 요청을 나타냅니다.|  
|`JsMemoryFailure`|실패한 할당 이벤트를 나타냅니다.|  
|`JsMemoryFree`|메모리 해제 이벤트를 나타냅니다.|  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)