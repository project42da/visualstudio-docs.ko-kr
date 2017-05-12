---
title: "delete 연산자(JavaScript) | Microsoft Docs"
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
  - "delete_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "배열 요소, 삭제"
  - "속성, 삭제"
  - "delete 연산자"
ms.assetid: 55c6487e-96ea-455b-a7ed-dc35c41ac2f3
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# delete 연산자(JavaScript)
개체에서 속성을 삭제하거나 배열에서 요소를 제거합니다.  
  
## 구문  
  
```  
delete expression  
```  
  
## 설명  
 `expression` 인수는 일반적으로 속성 이름 또는 배열 요소를 가져오는 올바른 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 식입니다.  
  
 `expression`의 결과가 개체이고, `expression`에 지정된 속성이 존재하고, 개체에서 삭제가 허용되지 않는 경우 `false`가 반환됩니다.  
  
 다른 모든 경우에는 `true`가 반환됩니다.  
  
## 예제  
 다음 예제에서는 배열에서 요소를 제거하는 방법을 보여 줍니다.  
  
```javascript  
// Create an array.  
var ar = new Array (10, 11, 12, 13, 14);  
  
// Remove an element from the array.  
delete ar[1];  
  
// Print the results.  
document.write ("element 1: " + ar[1]);  
document.write ("<br />");  
document.write ("array: " + ar);  
// Output:  
//  element 1: undefined  
//  array: 10,,12,13,14  
```  
  
## 예제  
 다음 예제에서는 개체에서 속성을 삭제하는 방법을 보여 줍니다.  
  
```javascript  
// Create an object and add expando properties.  
var myObj = new Object();  
myObj.name = "Fred";  
myObj.count = 42;  
  
// Delete the properties from the object.  
delete myObj.name;  
delete myObj["count"];  
  
// Print the results.  
document.write ("name: " + myObj.name);  
document.write ("<br />");  
document.write ("count: " + myObj.count);  
// Output:  
//  name: undefined  
//  count: undefined  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)