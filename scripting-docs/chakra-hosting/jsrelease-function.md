---
title: "JsRelease 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsRelease"
helpviewer_keywords: 
  - "JsRelease 함수"
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsRelease 함수
가비지 수집 개체에 대한 참조를 해제합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsRelease(  
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
 `JsAddRef`에서 만들어진 `JsRef` 핸들에 대한 참조를 제거합니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)