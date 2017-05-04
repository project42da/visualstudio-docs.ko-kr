---
title: "apply 메서드(Function)(JavaScript) | Microsoft Docs"
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
  - "apply"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Apply 메서드"
ms.assetid: b36df78e-b14b-46ca-b5cb-de752d80f40a
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# apply 메서드(Function)(JavaScript)
함수를 호출하여 지정된 개체를 함수의 `this` 값으로 대체하고 지정된 배열을 함수의 인수로 대체합니다.  
  
## 구문  
  
```  
apply([thisObj[,argArray]])  
```  
  
## 매개 변수  
 `thisObj`  
 선택 사항입니다.  `this` 개체로 사용될 개체입니다.  
  
 `argArray`  
 선택 사항입니다.  함수에 전달될 인수 집합입니다.  
  
## 설명  
 `argArray`가 올바른 개체가 아니면 "개체가 필요합니다." 오류가 발생합니다.  
  
 `argArray`나 `thisObj`가 제공되지 않으면 원래 `this` 개체가 `thisObj`로 사용되고 인수는 전달되지 않습니다.  
  
## 예제  
 다음 코드에서는 apply 메서드를 사용하는 방법을 보여 줍니다  
  
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
  
document.write("Function called with apply: <br/>");  
document.write(callMe.apply(3, [ 4, 5 ]));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with apply:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)