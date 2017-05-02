---
title: "call 메서드(Function)(JavaScript) | Microsoft Docs"
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
  - "call"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "call 메서드"
ms.assetid: fa356dec-48e6-4f75-8bf3-c1814a76818f
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# call 메서드(Function)(JavaScript)
개체의 메서드를 호출하여 다른 개체를 현재 개체로 대체합니다.  
  
## 구문  
  
```  
call([thisObj[, arg1[, arg2[,  [, argN]]]]])  
```  
  
## 매개 변수  
 `thisObj`  
 선택 사항입니다.  현재 개체로 사용될 개체입니다.  
  
 `arg1, arg2, , argN`  
 선택 사항입니다.  메서드에 전달될 인수 목록입니다.  
  
## 설명  
 `call` 메서드는 다른 개체 대신 메서드를 호출하는 데 사용됩니다.  이 메서드를 사용하여 함수의 `this` 개체를 원래 컨텍스트에서 `thisObj`로 지정된 새 개체로 변경할 수 있습니다.  
  
 `thisObj`가 제공되지 않으면 `global` 개체가 `thisObj`로 사용됩니다.  
  
## 예제  
 다음 코드는 `call` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
function callMe(arg1, arg2){  
    var s = "";  
  
    s += "this value: " + this;  
    s += "<br />";  
    for (i in callMe.arguments) {  
        s += "arguments: " + callMe.arguments[i];  
        s += "<br />";  
    }  
    return s;  
}  
  
document.write("Original function: <br/>");  
document.write(callMe(1, 2));  
document.write("<br/>");  
  
document.write("Function called with call: <br/>");  
document.write(callMe.call(3, 4, 5));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with call:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)   
 [apply 메서드\(Function\)](../../javascript/reference/apply-method-function-javascript.md)