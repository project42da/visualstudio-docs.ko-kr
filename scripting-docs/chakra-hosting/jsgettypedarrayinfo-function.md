---
title: "JsGetTypedArrayInfo 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# JsGetTypedArrayInfo 함수
형식화된 배열의 자주 사용되는 속성을 가져옵니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### 매개 변수  
 `typedArray`  
 형식화된 배열 인스턴스입니다.  
  
 `arrayType`  
 배열의 형식입니다.  
  
 `arrayBuffer`  
 배열의 `ArrayBuffer` 백스토어입니다.  
  
 `byteOffset`  
 배열에서 참조된 arrayBuffer의 시작 지점으로부터 오프셋\(바이트\)입니다.  
  
 `byteLength`  
 배열의 바이트 수입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)