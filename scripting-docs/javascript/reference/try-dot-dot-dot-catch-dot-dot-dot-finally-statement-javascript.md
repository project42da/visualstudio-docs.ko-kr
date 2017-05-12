---
title: "try...catch...finally 문(JavaScript) | Microsoft Docs"
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
  - "try_JavaScriptKeyword"
  - "finally_JavaScriptKeyword"
  - "catch_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "try-catch 예외 처리"
  - "try-catch 예외 처리, try-catch 예외 처리 정보"
  - "try-catch 예외 처리, catch 블록"
  - "try-catch 예외 처리, finally 블록"
ms.assetid: b7a0a54e-dfaa-4e41-bf25-bcaa43e601fb
caps.latest.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 28
---
# try...catch...finally 문(JavaScript)
한 블록에서 throw된 오류가 다른 블록에서 처리되는 코드 블록을 설정합니다.  `try` 블록 내부에서 throw되는 오류는 `catch` 블록에서 catch됩니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## 구문  
  
```  
try {  
    tryStatements  
}  
catch(exception){  
    catchStatements  
}  
finally {  
    finallyStatements  
}  
```  
  
## 매개 변수  
 `tryStatements`  
 필수 요소.  오류가 발생할 수 있는 문입니다.  
  
 `exception`  
 필수 요소.  임의의 변수 이름입니다.  `exception`의 초기 값은 throw된 오류의 값입니다.  
  
 `catchStatements`  
 선택적 요소.  연관된 `tryStatements`에서 발생한 오류를 처리하는 문입니다.  
  
 `finallyStatements`  
 선택적 요소.  모든 다른 오류 처리가 발생한 후 무조건 실행되는 문입니다.  
  
## 설명  
 `try...catch...finally` 문은 코드를 실행하는 동안 지정된 코드 블록에서 발생할 수 있는 일부 또는 모든 오류를 처리하는 방법을 제공합니다.  처리되지 않은 오류가 발생하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 일반 오류 메시지를 제공합니다.  
  
 `try` 블록에는 오류를 가져올 수 있는 코드가 포함되지만 `catch` 블록에는 일부 또는 모든 오류를 처리하는 코드가 포함됩니다.  `try` 블록에서 오류가 발생하면 프로그램 제어가 `catch` 블록에 전달됩니다.  `exception` 값은 `try` 블록에서 발생한 오류 값입니다.  오류가 발생하지 않으면 `catch` 블록의 코드가 실행되지 않습니다.  
  
 `throw` 문을 사용하여 오류를 다시 throw하면 오류를 다음 수준까지 전달할 수 있습니다.  
  
 `try` 블록의 모든 문이 실행되고 `catch` 블록에서 오류 처리가 수행되고 나면 오류 처리 여부와 관계없이 `finally` 블록의 문이 실행됩니다.  처리되지 않은 오류가 발생하지 않는 한\(예: **catch** 블록 내부 런타임 오류\) `finally` 블록의 코드는 반드시 실행됩니다.  
  
## 예제  
 다음 예제에서는 `ReferenceError` 예외를 throw하고 오류 이름과 해당 메시지를 표시합니다.  
  
```javascript  
try {  
    addalert("bad call");  
}  
catch(e) {  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF);  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
  
// Output:  
Error Message: 'addalert' is undefined  
Error Code: 5009  
Error Name: ReferenceError  
  
```  
  
## 예제  
 다음 예제에서는 오류를 다시 throw하는 방법과 중첩된 `try…catch` 블록의 실행을 보여 줍니다.  오류가 중첩된 `try` 블록에서 throw되면 오류를 다시 throw할 중첩된 `catch` 블록에 전달됩니다.  중첩된 `finally` 블록은 외부 `catch` 블록이 오류를 처리하기 전에, 그리고 외부 `finally` 블록 실행이 끝날 때 실행됩니다.  
  
```javascript  
try {  
    document.write("Outer try running...<br/>");  
  
    try {  
        document.write("Nested try running...<br/>");  
        throw new Error(301, "an error");  
    }  
    catch (e) {  
        document.write ("Nested catch caught " + e.message + "<br/>");  
        throw e;  
    }  
    finally {  
        document.write ("Nested finally is running...<br/>");  
    }  
}  
catch (e) {  
    document.write ("Outer catch caught " + e.message + "<br/>");  
}  
finally {  
    document.write ("Outer finally running");  
}  
  
// Output:  
// Outer try running...  
// Nested try running...  
// Nested catch caught error from nested try  
// Nested finally is running...  
// Outer catch caught error from nested try  
// Outer finally running  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
> [!NOTE]
>  Internet Explorer 8 표준 모드부터 `finally`가 실행되는 데 더 이상 **catch** 블록이 필요하지 않습니다.  
  
## 참고 항목  
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [Script Junkie 구성 마법사 샘플 앱](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)