---
title: "JsConstructObject 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsConstructObject"
helpviewer_keywords: 
  - "JsConstructObject 함수"
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsConstructObject 함수
함수를 생성자로 호출합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### 매개 변수  
 `function`  
 생성자로 호출할 함수입니다.  
  
 `arguments`  
 호출에 대한 인수입니다.  
  
 `argumentCount`  
 함수에 전달되는 인수 수입니다.  
  
 `result`  
 함수 호출에서 반환된 값입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)