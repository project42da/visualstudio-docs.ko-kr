---
title: "ScriptEngineBuildVersion 함수(JavaScript) | Microsoft Docs"
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
  - "ScriptEngineBuildVersion"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "ScriptEngineBuildVersion 함수"
ms.assetid: 7e255030-b0a3-420b-9c96-bb3e93c9333f
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# ScriptEngineBuildVersion 함수(JavaScript)
사용 중인 스크립팅 엔진의 빌드 버전 번호를 가져옵니다.  
  
## 구문  
  
```  
ScriptEngineBuildVersion()  
```  
  
## 설명  
 반환 값은 사용 중인 스크립트 언어에 대한 DLL\(동적 연결 라이브러리\)에 포함된 버전 정보에 직접 해당합니다.  
  
## 예제  
 다음 예제에서는 `ScriptEngineBuildVersion` 함수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
if(window.ScriptEngineBuildVersion) {  
    console.log(window.ScriptEngineBuildVersion());  
}  
  
// Output: <current build version>  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## 참고 항목  
 [ScriptEngine 함수](../../javascript/reference/scriptengine-function-javascript.md)   
 [ScriptEngineMajorVersion 함수](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [ScriptEngineMinorVersion 함수](../../javascript/reference/scriptengineminorversion-function-javascript.md)