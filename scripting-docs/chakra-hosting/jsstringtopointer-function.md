---
title: "JsStringToPointer 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsStringToPointer"
helpviewer_keywords: 
  - "JsStringToPointer 함수"
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsStringToPointer 함수
문자열 값의 문자열 포인터를 검색합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### 매개 변수  
 `value`  
 문자열 포인터로 변환할 문자열 값입니다.  
  
 `stringValue`  
 문자열 포인터입니다.  
  
 `stringLength`  
 문자열의 길이입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 이 함수는 문자열 값의 문자열 포인터를 검색합니다.  값 형식이 문자열이 아니면 `JsErrorInvalidArgument`에서 실패합니다.  반환된 문자열의 수명은 소스 값의 수명과 같지만 문자열 포인터는 값에 대한 참조로 간주하지 않으므로 수집되지 않습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)