---
title: "JsAddRef 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsAddRef"
helpviewer_keywords: 
  - "JsAddRef 함수"
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsAddRef 함수
가비지 수집 개체에 대한 참조를 추가합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### 매개 변수  
 `ref`  
 참조를 추가할 개체입니다.  
  
 `count`  
 개체의 새 참조 개수입니다\(null로 전달될 수 있음\).  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 스택에 저장되지 않는 `JsRef` 핸들에 대해 호출하면 됩니다.  `JsAddRef`를 호출하면 `JsRelease`가 호출될 때까지 `JsRef`가 참조하는 개체가 해제되지 않습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)