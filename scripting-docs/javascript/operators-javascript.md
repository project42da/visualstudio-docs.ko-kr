---
title: "연산자(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "JavaScript, 연산자"
ms.assetid: b8602b69-aba9-46e8-86e1-cb533ad41410
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 연산자(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 산술, 논리, 비트 및 할당 연산자 뿐만 아니라 다른 연산자도 사용할 수 있습니다.  설명과 예제는 특정 연산자에 대한 항목을 참조하십시오.  
  
## 계산 연산자  
  
|설명|기호|  
|--------|--------|  
|[단항 부정 연산자](../javascript/reference/subtraction-operator-decrement-javascript.md)|\-|  
|[Increment](../javascript/reference/increment-and-decrement-operators-javascript.md)|\+\+|  
|[Decrement](../javascript/reference/increment-and-decrement-operators-javascript.md)|\-\-|  
|[곱하기](../javascript/reference/multiplication-operator-decrement-javascript.md)|\*|  
|[나누기](../javascript/reference/division-operator-decrement-javascript.md)|\/|  
|[나머지 연산자](../javascript/reference/modulus-operator-decrementjavascript.md)|%|  
|[추가](../javascript/reference/addition-operator-decrement-javascript.md)|\+|  
|[빼기](../javascript/reference/subtraction-operator-decrement-javascript.md)|\-|  
  
## 논리 연산자  
  
|설명|기호|  
|--------|--------|  
|[논리 부정 연산자](../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|\!|  
|[보다 작음](../javascript/reference/comparison-operators-javascript.md)|\<|  
|[보다 큼](../javascript/reference/comparison-operators-javascript.md)|\>|  
|[작거나 같음](../javascript/reference/comparison-operators-javascript.md)|\<\=|  
|[크거나 같음](../javascript/reference/comparison-operators-javascript.md)|\>\=|  
|[같음](../javascript/reference/comparison-operators-javascript.md)|\=\=|  
|[같지 않음](../javascript/reference/comparison-operators-javascript.md)|\!\=|  
|[논리곱](../javascript/reference/logical-and-operator-decrement-javascript.md)|&&|  
|[논리합](../javascript/reference/logical-or-operator-decrement-javascript.md)|&#124;&#124;|  
|[조건\(삼항\)](../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|?:|  
|[쉼표](../javascript/reference/comma-operator-decrement-javascript.md)|,|  
|[완전 같음](../javascript/reference/comparison-operators-javascript.md)|\=\=\=|  
|[완전 같지 않음](../javascript/reference/comparison-operators-javascript.md)|\!\=\=|  
  
## 비트 연산자  
  
|설명|기호|  
|--------|--------|  
|[비트 NOT](../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|~|  
|[비트 왼쪽 시프트](../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|\<\<|  
|[비트 오른쪽 시프트](../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|\>\>|  
|[부호 없는 오른쪽 시프트](../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|\>\>\>|  
|[비트 AND](../javascript/reference/bitwise-and-operator-decrement-javascript.md)|&|  
|[비트 XOR](../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|^|  
|[비트 OR](../javascript/reference/bitwise-or-operator-decrement-javascript.md)|&#124;|  
  
## 할당 연산자  
  
|설명|기호|  
|--------|--------|  
|[할당 연산](../javascript/reference/assignment-operator-decrement-equal-javascript.md)|\=|  
|[복합 할당](../javascript/reference/compound-assignment-operators-javascript.md)|*OP*\=\(예: \+\= 및 &\=\)|  
  
## 기타 연산자  
  
|설명|기호|  
|--------|--------|  
|[삭제](../javascript/reference/delete-operator-decrementjavascript.md)|삭제|  
|[typeof](../javascript/reference/typeof-operator-decrementjavascript.md)|typeof|  
|[void](../javascript/reference/void-operator-decrementjavascript.md)|void|  
|[instanceof](../javascript/reference/instanceof-operator-decrementjavascript.md)|instanceof|  
|[new](../javascript/reference/new-operator-decrementjavascript.md)|new|  
|[in](../javascript/reference/in-operator-decrementjavascript.md)|in|  
  
## 같음 및 완전 같음  
 \=\=\(같음\) 및 \=\=\=\(완전 같음\)의 경우 같음 연산자가 같음을 확인하기 전에 서로 다른 형식의 값을 강제 변환한다는 차이점이 있습니다.  예를 들어 문자열 "1"과 숫자 1을 비교하면 두 값이 같은 것으로 비교됩니다.  반면에 완전 같음 연산자의 경우 값을 서로 다른 형식으로 강제 변환하지 않기 때문에 문자열 "1"이 숫자 1과 같은 것으로 비교되지 않습니다.  
  
 기본 문자열, 숫자 및 부울은 해당 값으로 비교됩니다.  같은 값을 가진 경우 같은 것입니다.  `Array`, `Function`, `String`, **Number**, `Boolean`, **Error,** `Date`, `RegExp` 등의 개체는 참조를 사용하여 비교합니다.  이러한 형식의 두 변수가 동일한 값을 갖더라도 완전히 같은 개체를 참조하는 경우에만 같은 것입니다.  
  
 예를 들면 다음과 같습니다.  
  
```javascript  
// Two strings with the same value.  
var string1 = "Hello";  
var string2 = "Hello";  
  
// Two String objects with the same value.  
var StringObject1 = new String(string1);  
var StringObject2 = new String(string2);  
  
if (string1 == string2)  
    document.write("string1 is equal to string2 <br/>");  
  
if (StringObject1 != StringObject2)  
    document.write("StringObject1 is not equal to StringObject2 <br/>");  
  
// To compare the values of String objects, use the toString() or valueOf() methods.  
if (StringObject1.valueOf() == StringObject2.valueOf())  
    document.write("The value of StringObject1 is equal to the value of StringObject2");  
  
//Output:  
// string1 is equal to string2   
// StringObject1 is not equal to StringObject2   
// The value of StringObject1 is equal to the value of StringObject2  
  
```