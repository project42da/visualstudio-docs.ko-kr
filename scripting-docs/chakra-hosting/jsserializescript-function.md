---
title: "JsSerializeScript 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsSerializeScript"
helpviewer_keywords: 
  - "JsSerializeScript 함수"
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsSerializeScript 함수
구문 분석된 스크립트를 다시 사용할 수 있는 버퍼로 serialize합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### 매개 변수  
 `script`  
 serialize할 스크립트입니다.  
  
 `buffer`  
 serialize된 스크립트를 삽입할 버퍼입니다.  null일 수 있습니다.  
  
 `bufferSize`  
 입력 시 버퍼 크기\(바이트\), 종료 시 버퍼 크기\(바이트\), serialize된 스크립트를 저장하는 데 필요합니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 `JsSerializeScript`는 스크립트를 구문 분석하고 스크립트의 구문 분석된 양식을 런타임 독립적인 형식으로 저장합니다.  스크립트를 다시 구문 분석할 필요 없이 런타임에 serialize된 스크립트를 deserialize할 수 있습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)