---
title: "JsNumberToInt 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# JsNumberToInt 함수
숫자 값의 `int` 값을 검색합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### 매개 변수  
 `value`  
 `int` 값으로 변환할 숫자 값입니다.  
  
 `intValue`  
 `int` 값입니다.  
  
## 반환 값  
  
## 설명  
 이 함수는 숫자 값의 값을 검색하고 `int` 값으로 변환합니다.  값 형식이 숫자가 아니면 `JsErrorInvalidArgument`에서 실패합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)