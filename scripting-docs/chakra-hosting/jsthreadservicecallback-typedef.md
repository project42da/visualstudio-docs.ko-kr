---
title: "JsThreadServiceCallback Typedef | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# JsThreadServiceCallback Typedef
스레드 서비스 콜백입니다.  
  
## 구문  
  
```  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### 매개 변수  
 callback  
 백그라운드 작업 항목에 대한 콜백입니다.  
  
 callbackData  
 콜백에 전달되는 데이터 인수입니다.  
  
## 설명  
 호스트는 JsCreateRuntime 호출 시 백그라운드 스레드 서비스를 지정할 수 있습니다.  지정된 경우 백그라운드 작업 항목은 이 콜백을 사용하여 호스트에 전달됩니다.  호스트는 백그라운드 작업 항목 실행을 즉시 시작하고 true를 반환하거나, false를 반환하고 런타임이 스레드에 있는 작업 항목을 처리합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)