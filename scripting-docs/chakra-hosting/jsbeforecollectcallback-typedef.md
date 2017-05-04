---
title: "JsBeforeCollectCallback Typedef | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# JsBeforeCollectCallback Typedef
수집 전에 호출된 콜백입니다.  
  
## 구문  
  
```  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### 매개 변수  
 callbackState  
 JsSetBeforeCollectCallback에 전달된 상태입니다.  
  
## 설명  
 이 콜백을 등록하려면 JsSetBeforeCollectCallback을 사용합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)