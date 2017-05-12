---
title: "JsStartDebugging 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsStartDebugging"
helpviewer_keywords: 
  - "JsStartDebugging 함수"
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# JsStartDebugging 함수
현재 컨텍스트에서 디버깅을 시작합니다.  
  
## 구문  
  
```  
// Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### 매개 변수  
 `debugApplication`  
 디버깅에 사용할 디버그 응용 프로그램입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 호스트는 이 API를 사용하기 전에 `CoInitializeEx`가 `COINIT_MULTITHREADED` 또는 `COINIT_APARTMENTTHREADED`와 함께 한 번 이상 호출되었는지 확인해야 합니다.  
  
 `debugApplication` 매개 변수는 가장자리 모드에서 지원되지 않습니다.  가장자리 모드에서 이 API를 사용하는 방법에 대한 자세한 내용은 [Edge 및 레거시 엔진을 대상으로 지정](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)을 참조하세요.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)