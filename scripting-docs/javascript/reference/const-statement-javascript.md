---
title: "const 문(JavaScript) | Microsoft Docs"
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
  - "const_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "변수 선언, const 문"
  - "const 문"
ms.assetid: 3ad0840f-437f-4163-9571-86ecc5ddb987
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# const 문(JavaScript)
상수 값을 사용하여 블록 범위 변수를 선언합니다.  
  
## 구문  
  
```  
const constant1 = value1  
```  
  
#### 매개 변수  
 `constant1`  
 선언 중인 변수의 이름입니다.  
  
 `value1`  
 변수에 할당된 초기 값입니다.  
  
## 설명  
 `const` 문을 사용하여 변수를 상수 값으로 선언합니다. 범위는 변수가 선언되는 블록으로 제한됩니다.  변수의 값은 변경할 수 없습니다.  
  
 `const`를 사용하여 선언한 변수는 선언할 때 초기화해야 합니다.  
  
## 예제  
 다음 예제는 `const` 문의 사용 예를 보여 줍니다.  
  
```javascript  
var c = 10;  
{  
    const c = 2;  
   // At this point, c = 2.  
}  
// At this point, c = 10.  
  
// Additional ways to declare a variable using const.  
const name = "Thomas Jefferson";  
const answer = 42, numpages = 10;  
const myarray = new Array();  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [let 문](../../javascript/reference/let-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)