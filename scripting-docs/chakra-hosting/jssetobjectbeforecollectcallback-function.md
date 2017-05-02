---
title: "JsSetObjectBeforeCollectCallback 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# JsSetObjectBeforeCollectCallback 함수
개체의 가비지 수집 전에 런타임에서 호출되는 콜백 함수를 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### 매개 변수  
 `ref`  
 콜백을 등록할 개체입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
 `objectBeforeCollectCallback`  
 설정되는 콜백 함수입니다.  null을 사용하여 이전에 등록된 콜백을 지웁니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 콜백은 현재 런타임 스레드에서 호출되므로 콜백이 완료될 때까지 실행이 차단됩니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)