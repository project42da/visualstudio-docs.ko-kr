---
title: "Object.getPrototypeOf 함수(JavaScript) | Microsoft Docs"
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
helpviewer_keywords: 
  - "getPrototypeOf 함수[JavaScript]"
  - "Object.getPrototypeOf 함수[JavaScript]"
ms.assetid: 1c59cd7a-a7e2-4c5c-83ec-e6bd2b104d9f
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Object.getPrototypeOf 함수(JavaScript)
개체의 프로토타입을 반환합니다.  
  
## 구문  
  
```javascript  
Object.getPrototypeOf(object)  
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  프로토타입을 참조하는 개체입니다.  
  
## 반환 값  
 `object` 인수의 프로토타입입니다.  프로토타입도 개체입니다.  
  
## 예외  
 `object` 인수가 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 예제  
 다음 예제에서는 `Object.getPrototypeOf` 함수의 사용법을 보여 줍니다.  
  
```javascript  
// Create a constructor function.  
function Pasta(grain, width) {  
    this.grain = grain;  
    this.width = width;  
}  
// Create an object from the pasta constructor.  
var spaghetti = new Pasta("wheat", 0.2);  
  
// Obtain the prototype from the object.  
var proto = Object.getPrototypeOf(spaghetti);  
  
// Add a property to the prototype and validate that  
// the original object has the property.  
proto.foodgroup = "carbohydrates";  
document.write(spaghetti.foodgroup + " ");  
  
// Verify that the prototype obtained from the object  
// is the same as the prototype of the constructor.  
var result = (proto === Pasta.prototype);  
document.write(result + " ");  
  
// Verify that prototype obtained from the object  
// is a prototype of the original object.  
var result = proto.isPrototypeOf(spaghetti);  
document.write(result);  
  
// Output: carbohydrates true true  
```  
  
## 예제  
 다음 예제에서는 데이터 형식의 유효성 검사를 수행하는 데 `Object.getPrototypeOf` 함수를 사용합니다.  
  
```javascript  
var reg = /a/;  
var result = (Object.getPrototypeOf(reg) === RegExp.prototype);  
document.write(result + " ");  
  
var err = new Error("an error");  
var result = (Object.getPrototypeOf(err) === Error.prototype);  
document.write(result);  
  
// Output: true true  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)   
 [isPrototypeOf 메서드\(Object\)](../../javascript/reference/isprototypeof-method-object-javascript.md)