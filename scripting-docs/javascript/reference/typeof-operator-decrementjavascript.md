---
title: "typeof 연산자(JavaScript) | Microsoft Docs"
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
  - "typeof_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "typeof 연산자"
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# typeof 연산자(JavaScript)
식의 데이터 형식을 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## 설명  
 *expression* 인수는 형식 정보를 찾은 식입니다.  
  
 `typeof` 연산자는 형식 정보를 문자열로 반환합니다.  `typeof`는 "number", "string", "boolean", "object", "function" 및 "undefined"의 6가지 값을 반환할 수 있습니다.  
  
 `typeof` 구문에서 괄호는 선택 사항입니다.  
  
## 예제  
 다음 예제에서는 변수의 데이터 형식을 테스트합니다.  
  
```javascript  
var index = 5;  
var result = (typeof index === 'number');  
// Output: true  
  
var description = "abc";  
var result = (typeof description === 'string');  
// Output: true  
```  
  
## 예제  
 다음 예제에서는 선언된 변수와 선언되지 않은 변수의 `undefined` 데이터 형식을 테스트합니다.  
  
```javascript  
var declared;  
var result = (declared === undefined);  
// Output: true  
  
var result = (typeof declared === 'undefined');  
// Output: true  
  
var result = (typeof notDeclared === 'undefined')  
// Output: true  
  
var obj = {};  
var result = (typeof obj.propNotDeclared === 'undefined');  
// Output: true  
  
// An undeclared variable cannot be used in a comparison without  
// the typeof operator, so the next line generates an error.  
//  var result = (notDeclared === undefined);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [Array.isArray 함수](../../javascript/reference/array-isarray-function-javascript.md)   
 [Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined 상수](../../javascript/reference/undefined-constant-javascript.md)   
 [비교 연산자](../../javascript/reference/comparison-operators-javascript.md)   
 [데이터 형식](../../javascript/data-types-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)