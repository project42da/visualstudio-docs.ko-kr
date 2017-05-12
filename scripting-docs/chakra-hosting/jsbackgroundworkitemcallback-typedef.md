---
title: "JsBackgroundWorkItemCallback Typedef | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# JsBackgroundWorkItemCallback Typedef
백그라운드 작업 항목 콜백입니다.  
  
## 구문  
  
```  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### 매개 변수  
 callbackData  
 스레드 서비스에 전달되는 데이터 인수입니다.  
  
## 설명  
 이 데이터 인수는 호스트의 스레드 서비스\(제공된 경우\)에 전달되어 호스트가 선택한 백그라운드 스레드에 대해 작업 항목 콜백을 호출할 수 있도록 합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)