---
title: "연산자(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, operators
ms.assetid: b8602b69-aba9-46e8-86e1-cb533ad41410
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a3068a609da2468c59066ccd38f6de87cef1ed17
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="operators-javascript"></a>연산자(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 산술, 논리, 비트 연산, 할당 및 일부 기타 연산자를 포함한 모든 범위의 연산자가 있습니다. 설명 및 예제를 보려면 특정 연산자에 대한 항목을 참조하세요.  
  
## <a name="computational-operators"></a>계산 연산자  
  
|설명|기호|  
|-----------------|------------|  
|[단항 부정](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
|[증분](../javascript/reference/increment-and-decrement-operators-javascript.md)|++|  
|[감소](../javascript/reference/increment-and-decrement-operators-javascript.md)|--|  
|[곱하기](../javascript/reference/multiplication-operator-decrement-javascript.md)|*|  
|[나누기](../javascript/reference/division-operator-decrement-javascript.md)|/|  
|[나머지 산술](../javascript/reference/modulus-operator-decrementjavascript.md)|%|  
|[더하기](../javascript/reference/addition-operator-decrement-javascript.md)|+|  
|[빼기](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
  
## <a name="logical-operators"></a>논리 연산자  
  
|설명|기호|  
|-----------------|------------|  
|[논리적 NOT](../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|!|  
|[보다 작음](../javascript/reference/comparison-operators-javascript.md)|\<|  
|[보다 큼](../javascript/reference/comparison-operators-javascript.md)|>|  
|[작거나 같음](../javascript/reference/comparison-operators-javascript.md)|\<=|  
|[크거나 같음](../javascript/reference/comparison-operators-javascript.md)|>=|  
|[같음](../javascript/reference/comparison-operators-javascript.md)|==|  
|[같지 않음](../javascript/reference/comparison-operators-javascript.md)|!=|  
|[논리적 AND](../javascript/reference/logical-and-operator-decrement-javascript.md)|&&|  
|[논리적 OR](../javascript/reference/logical-or-operator-decrement-javascript.md)|&#124;&#124;|  
|[조건부(삼항)](../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|?:|  
|[쉼표](../javascript/reference/comma-operator-decrement-javascript.md)|,|  
|[완전 같음](../javascript/reference/comparison-operators-javascript.md)|===|  
|[완전 같지 않음](../javascript/reference/comparison-operators-javascript.md)|!==|  
  
## <a name="bitwise-operators"></a>비트 연산자  
  
|설명|기호|  
|-----------------|------------|  
|[비트 NOT](../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|~|  
|[비트 왼쪽 시프트](../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|<\<|  
|[비트 오른쪽 시프트](../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|>>|  
|[부호 없는 오른쪽 시프트](../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|>>>|  
|[비트 AND](../javascript/reference/bitwise-and-operator-decrement-javascript.md)|&|  
|[비트 XOR](../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|^|  
|[비트 OR](../javascript/reference/bitwise-or-operator-decrement-javascript.md)|&#124;|  
  
## <a name="assignment-operators"></a>할당 연산자  
  
|설명|기호|  
|-----------------|------------|  
|[할당](../javascript/reference/assignment-operator-decrement-equal-javascript.md)|=|  
|[복합 할당](../javascript/reference/compound-assignment-operators-javascript.md)|*연산자*=(예: += 및 &=)|  
  
## <a name="miscellaneous-operators"></a>기타 연산자  
  
|설명|기호|  
|-----------------|------------|  
|[delete](../javascript/reference/delete-operator-decrementjavascript.md)|삭제|  
|[typeof](../javascript/reference/typeof-operator-decrementjavascript.md)|typeof|  
|[void](../javascript/reference/void-operator-decrementjavascript.md)|void|  
|[instanceof](../javascript/reference/instanceof-operator-decrementjavascript.md)|instanceof|  
|[new](../javascript/reference/new-operator-decrementjavascript.md)|new|  
|[in](../javascript/reference/in-operator-decrementjavascript.md)|의|  
  
## <a name="equality-and-strict-equality"></a>같음 및 완전 같음  
 ==(같음)과 ===(완전 같음)의 차이는 같음 연산자가 같음을 확인하기 전에 다른 형식의 값을 강제 변환한다는 것입니다. 예를 들어 문자열 "1"과 숫자 1을 비교할 때 true로 비교됩니다. 반면에, 완전 같음 연산자는 값을 다른 형식으로 강제 변환하지 않으므로 문자열 "1"을 숫자 1과 동일하게 비교합니다.  
  
 기본 문자열, 숫자 및 부울 값이 값으로 비교됩니다. 동일한 값이 있는 경우 같음입니다. 개체(`Array`, `Function`, `String`, **Number**, `Boolean`, **Error**, `Date` 및 `RegExp` 개체)는 참조로 비교됩니다. 이러한 형식의 두 변수가 동일한 값을 갖고 있어도 정확히 동일한 개체를 참조하는 경우에만 동일합니다.  
  
 예:  
  
```JavaScript  
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