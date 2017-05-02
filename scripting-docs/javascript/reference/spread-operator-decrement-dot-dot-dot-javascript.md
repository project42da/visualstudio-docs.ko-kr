---
title: "스프레드 연산자(...)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 10263a4c-bd27-4d87-9917-fb4b6bf373db
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# 스프레드 연산자(...)(JavaScript)
배열 리터럴의 일부를 반복 가능한 식\(다른 배열 리터럴 등\)에서 초기화하거나 식을 함수 호출에서 여러 인수로 확장할 수 있습니다.  
  
## 구문  
  
```  
var array = [[arg0ToN ,] ...iterable [, arg0ToN]]  
func([args ,] ...iterable [, args | ...iterable])  
  
```  
  
## 매개 변수  
 `iterable`  
 필수.  반복 가능한 개체입니다.  
  
 `arg0ToN`  
 선택 사항입니다.  하나 이상의 배열 리터럴 요소입니다.  
  
 `args`  
 선택 사항입니다.  함수에 대한 하나 이상의 인수입니다.  
  
## 설명  
 반복기에 대한 자세한 내용은 [반복기 및 생성기](../../javascript/advanced/iterators-and-generators-javascript.md)를 참조하세요.  rest 매개 변수로 스프레드 연산자 사용하기에 대한 자세한 내용은 [함수](../../javascript/functions-javascript.md)를 참조하세요.  
  
## 예제  
 다음 코드 예제에서는 스프레드 연산자의 사용이 `concat` 메서드의 사용과 대조를 이룹니다.  
  
```javascript  
var a, b, c, d, e;  
a = [1,2,3];  
b = "dog";  
c = [42, "cat"];  
  
// Using the concat method.  
d = a.concat(b, c);  
  
// Using the spread operator.  
e = [...a, b, ...c];  
  
console.log(d);  
console.log(e);  
  
// Output:  
// 1, 2, 3, "dog", 42, "cat"  
// 1, 2, 3, "dog", 42, "cat"  
```  
  
## 예제  
 다음 코드 예제에서는 함수 호출에서 스프레드 연산자를 사용하는 방법을 보여줍니다.  이 예제에서는 두 개의 배열 리터럴이 스프레드 연산자를 사용하여 함수로 전달되며 배열은 여러 인수에 확장됩니다.  
  
```javascript  
function f(a, b, c, x, y, z) {  
  return a + b + c + x + y + z;  
}  
  
var args = [1, 2, 3];  
console.log(f(...args, 4, ...[5, 6]));  
  
// Output:  
// 21  
  
```  
  
## 예제  
 스프레드 연산자를 사용하여 이전에 `apply` 사용을 필요로 한 코드를 간소화할 수 있습니다.  
  
```javascript  
function f(x, y, z) {  
    return x + y + z;  
}  
  
var args = [1, 2, 3];  
  
// Old method  
func.apply(this, args);  
// New method  
func(...args);  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)