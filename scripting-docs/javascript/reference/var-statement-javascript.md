---
title: "var 문(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "var_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "변수 선언, var 문"
  - "var 문"
ms.assetid: 56f900af-a5c4-4667-9664-5956d30f0aae
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# var 문(JavaScript)
변수를 선언합니다.  
  
## 구문  
  
```  
var variable1 = value1  
```  
  
## 매개 변수  
 `variable1`  
 선언 중인 변수의 이름입니다.  
  
 `value1`  
 변수에 할당된 초기 값입니다.  
  
## 설명  
 `var` 문을 사용하여 변수를 선언합니다.  변수를 선언할 때 또는 나중에 스크립트로 변수에 값을 할당할 수 있습니다.  
  
 변수는 스크립트에 처음 나타날 때 선언됩니다.  
  
 `var` 키워드를 사용하지 않고 변수를 선언한 다음 변수에 값을 할당할 수 있습니다.  이렇게 하는 것을 암시적 선언이라고 합니다. 그러나 이 방법은 사용하지 않는 것이 좋습니다.  암시적 선언을 사용하면 변수 범위가 전역으로 설정됩니다.  그러나 프로시저 수준에서 변수를 선언할 때는 일반적으로 전역 범위로 설정되는 것을 원치 않는 경우입니다.  변수의 전역 범위 설정을 방지하려면 변수 선언에서 `var` 키워드를 사용해야 합니다.  
  
 `var` 문에서 변수를 초기화하지 않을 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값 `undefined`가 자동으로 할당됩니다.  
  
## 예제  
 다음 예제에서는 `var` 문을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var index;  
var name = "Thomas Jefferson";  
var answer = 42, counter, numpages = 10;  
var myarray = new Array();  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)