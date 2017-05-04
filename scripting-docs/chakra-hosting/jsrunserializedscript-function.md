---
title: "JsRunSerializedScript 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsRunSerializedScript"
helpviewer_keywords: 
  - "JsRunSerializedScript 함수"
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# JsRunSerializedScript 함수
serialize된 스크립트를 실행합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 매개 변수  
 `script`  
 serialize된 스크립트의 소스 코드입니다.  
  
 `buffer`  
 serialize된 스크립트입니다.  
  
 `sourceContext`  
 디버깅 가능한 스크립트 컨텍스트에서 사용될 수 있는 스크립트를 식별하는 쿠키입니다.  
  
 `sourceUrl`  
 스크립트를 가져온 위치입니다.  
  
 `result`  
 스크립트를 실행한 결과입니다\(있는 경우\).  이 매개 변수는 null일 수 있습니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 버퍼가 스크립팅 엔진에 의해 메모리에서 지속되지 않으므로 버퍼가 스크립트를 실행하는 데 사용될 수 있는 동안에는 코드에서 버퍼를 활성 상태로 유지해야 합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)