---
title: "JsSetProjectionEnqueueCallback 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# JsSetProjectionEnqueueCallback 함수
호출자 필요 스레드에 다시 프로젝션 완료를 호출하기 위해 사용할 콜백을 설정합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### 매개 변수  
 `projectionEnqueueContext`  
 프로젝션 완료가 백그라운드 스레드에서 발생할 때마다 호출되는 콜백입니다.  
  
 `callbackState`  
 `projectionEnqueueContext`에 제공되는 응용 프로그램 컨텍스트입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 다른 COM 아파트 또는 동일한 MTA의 다른 스레드에서 호출을 요청해야 합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
> [!CAUTION]
>  PInvoke는 현재 이 API에 대해 지원되지 않습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)