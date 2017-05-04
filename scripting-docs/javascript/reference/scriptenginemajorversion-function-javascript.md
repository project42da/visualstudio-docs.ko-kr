---
title: "ScriptEngineMajorVersion 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ScriptEngineMajorVersion"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "ScriptEngineMajorVersion 함수"
ms.assetid: 3e251bce-1e14-4cb5-b79f-53845d1920fd
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# ScriptEngineMajorVersion 함수(JavaScript)
사용 중인 스크립팅 엔진의 주 버전 번호를 가져옵니다.  
  
## 구문  
  
```  
ScriptEngineMajorVersion()  
```  
  
## 설명  
 반환 값은 사용 중인 스크립트 언어에 대한 DLL\(동적 연결 라이브러리\)에 포함된 버전 정보에 직접 해당합니다.  
  
## 예제  
 다음 예제에서는 `ScriptEngineMajorVersion` 함수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
if (window.ScriptEngineMajorVersion) {  
    console.log(window.ScriptEngine());   
}  
  
Output: <current major version>  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## 참고 항목  
 [ScriptEngine 함수](../../javascript/reference/scriptengine-function-javascript.md)   
 [ScriptEngineBuildVersion 함수](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [ScriptEngineMinorVersion 함수](../../javascript/reference/scriptengineminorversion-function-javascript.md)