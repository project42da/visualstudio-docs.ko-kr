---
title: "let 문(JavaScript) | Microsoft Docs"
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
  - "let_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "let 문"
  - "변수 선언, let 문"
ms.assetid: c7e4f8a9-8f54-47b6-aed2-956959c1ecfd
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# let 문(JavaScript)
블록 범위 변수를 선언합니다.  
  
## 구문  
  
```  
let variable1 = value1  
```  
  
#### 매개 변수  
 `variable1`  
 선언 중인 변수의 이름입니다.  
  
 `value1`  
 변수에 할당된 초기 값입니다.  
  
## 설명  
 `let` 문을 사용하여 변수를 선언합니다. 범위는 변수가 선언되는 블록으로 제한됩니다.  변수를 선언할 때 또는 나중에 스크립트로 변수에 값을 할당할 수 있습니다.  
  
 `let`을 사용하여 선언한 변수는 선언 전에 사용할 수 없으며, 그렇지 않으면 오류가 발생합니다.  
  
 `let` 문에서 변수를 초기화하지 않을 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값 `undefined`가 자동으로 할당됩니다.  
  
## 예제  
 다음 예제는 `let` 문의 사용 예를 보여 줍니다.  
  
```javascript  
var  l = 10;  
{  
    let l = 2;  
   // At this point, l = 2.  
}  
// At this point, l = 10.  
  
// Additional ways to declare a variable using let.  
let index;  
let name = "Thomas Jefferson";  
let answer = 42, counter, numpages = 10;  
let myarray = new Array();  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [const 문](../../javascript/reference/const-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)