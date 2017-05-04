---
title: "debugger 문(JavaScript) | Microsoft Docs"
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
  - "debugger_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "debugger 문"
ms.assetid: c6d2e193-c1f7-4fb3-8a4e-cc9823174ae4
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# debugger 문(JavaScript)
실행을 일시 중단합니다.  
  
## 구문  
  
```  
debugger  
```  
  
## 설명  
 프로시저 내의 임의 위치에 `debugger` 문을 사용하여 실행을 일시 중단할 수 있습니다.  `debugger` 문을 사용하는 것은 코드에 중단점을 설정하는 것과 비슷합니다.  
  
 `debugger` 문은 실행을 일시 중단하지만 파일을 닫거나 변수를 지우지 않습니다.  
  
> [!NOTE]
>  스크립트를 디버그하지 않는 경우 `debugger` 문은 아무런 영향을 주지 않습니다.  
  
## 예제  
 다음 예제에서는 `debugger` 문을 사용하여 `for` 루프를 통해 반복되는 각 실행을 일시 중단합니다.  
  
> [!NOTE]
>  이 예제를 실행하려면 스크립트 디버거를 설치하고 스크립트를 디버그 모드로 실행해야 합니다.  
>   
>  Internet Explorer 8에는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거가 포함됩니다.  이전 버전의 Internet Explorer를 사용 중인 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
```javascript  
for(i = 1; i<5; i++) {  
   // Print i to the Output window.  
   Debug.write("loop index is " + i);  
   // Wait for user to resume.  
   debugger  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [JavaScript 문](../../javascript/reference/javascript-statements.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)