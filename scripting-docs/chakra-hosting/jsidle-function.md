---
title: "JsIdle 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsIdle"
helpviewer_keywords: 
  - "JsIdle 함수"
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# JsIdle 함수
수행해야 할 유휴 처리를 수행하도록 런타임에 알립니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### 매개 변수  
 `nextIdleTick`  
 수행할 추가 유휴 작업이 있을 다음 시스템 틱입니다.   null일 수 있습니다.  수행할 예정 유휴 작업이 없는 경우 최대 틱 수를 반환합니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 현재 런타임에 대한 유휴 처리가 사용하도록 설정된 경우 `JsIdle`을 호출하면 호스트가 유휴 상태이고 런타임이 메모리 정리 작업을 수행할 수 있음을 현재 런타임에 알립니다.  
  
 `JsIdle`은 런타임이 수행할 추가 유휴 작업이 있을 때까지 시스템 틱 수를 반환할 수도 있습니다.  이 틱 수가 전달되기 전에 `JsIdle`을 호출하면 작업이 수행되지 않습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)