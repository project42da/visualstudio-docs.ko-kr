---
title: "JsEnumerateHeap 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsEnumerateHeap"
helpviewer_keywords: 
  - "JsEnumerateHeap 함수"
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsEnumerateHeap 함수
현재 컨텍스트의 힙을 열거합니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### 매개 변수  
 `enumerator`  
 힙 열거자입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 힙이 열거되는 동안에는 현재 컨텍스트를 제거할 수 없고 컨텍스트 상태를 수정하기 위한 모든 호출은 힙 열거자가 해제될 때까지 실패합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 데스크톱 앱에서 지원되지만 스토어 앱에서는 지원되지 않습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)