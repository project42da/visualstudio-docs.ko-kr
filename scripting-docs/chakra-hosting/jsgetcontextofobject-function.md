---
title: "JsGetContextOfObject 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# JsGetContextOfObject 함수
개체가 속하는 스크립트 컨텍스트를 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### 매개 변수  
 `object`  
 컨텍스트를 가져올 개체입니다.  
  
 `context`  
 개체가 속한 컨텍스트입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)