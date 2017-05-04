---
title: "function 문(JavaScript) | Microsoft Docs"
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
  - "function_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "함수 선언"
  - "함수 선언, 구문"
  - "function 문"
  - "new 연산자"
ms.assetid: cc9cfd43-1305-41c8-ad67-545d20f4fafe
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# function 문(JavaScript)
새 함수를 선언합니다.  
  
## 구문  
  
```  
function functionname ([arg1 [, arg2 [,...[, argN]]]]) {  
    statements  
}   
```  
  
## 매개 변수  
 `functionname`  
 필수 요소.  함수의 이름입니다.  
  
 `arg1...argN`  
 선택 사항입니다.  함수가 이해하는 인수의 선택적 목록으로, 쉼표로 구분됩니다.  
  
 `statements`  
 선택 사항입니다.  하나 이상의 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문입니다.  
  
## 설명  
 `function` 문을 통해 나중에 사용할 함수를 선언합니다.  `statements`에 포함된 코드는 스크립트의 다른 부분에서 함수를 호출할 때까지 실행되지 않습니다.  
  
 함수에서 값을 반환하기 위해 [return](../../javascript/reference/return-statement-javascript.md) 문이 사용됩니다.  프로그램에서 함수의 끝에 도달하면 반환되므로 `return` 문을 사용할 필요가 없습니다.  함수에서 `return` 문이 실행되지 않거나 `return` 문에 식이 없으면 `undefined` 값이 반환됩니다.  
  
> [!NOTE]
>  함수를 호출할 때는 반드시 괄호와 필수 인수를 포함해야 합니다.  괄호 없이 함수를 호출하면 함수의 결과 대신 함수에 대한 참조가 반환됩니다.  
  
## 예제  
 다음 예제에서는 `function` 문의 사용법을 보여 줍니다.  
  
```javascript  
function myfunction (arg1, arg2) {  
    var r = arg1 * arg2;  
    return(r);  
}  
```  
  
## 예제  
 변수에 함수를 할당할 수 있습니다.  다음 예제에서 이 과정을 보여 줍니다.  
  
```javascript  
function AddFive(x) {  
    return x + 5;  
}  
  
function AddTen(x) {  
    return x + 10;  
}  
  
var condition = false;  
  
var MyFunc;  
if (condition) {  
    MyFunc = AddFive;  
}  
else {  
    MyFunc = AddTen;  
}  
  
var result = MyFunc(123);  
// Output: 133  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)