---
title: "JsNumberToDouble 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsNumberToDouble"
helpviewer_keywords: 
  - "JsNumberToDouble 함수"
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsNumberToDouble 함수
숫자 값의 `double` 값을 검색합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### 매개 변수  
 `value`  
 `double` 값으로 변환할 숫자 값입니다.  
  
 `doubleValue`  
 `double` 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 이 함수는 숫자 값의 값을 검색합니다.  값 형식이 숫자가 아니면 `JsErrorInvalidArgument`에서 실패합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)