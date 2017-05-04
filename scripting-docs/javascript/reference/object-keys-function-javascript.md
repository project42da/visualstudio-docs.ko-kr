---
title: "Object.keys 함수(JavaScript) | Microsoft Docs"
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
  - "keys 메서드[JavaScript]"
  - "Object.keys 메서드[JavaScript]"
ms.assetid: cf4a7daf-cf28-4467-bc6b-f7f106ec3876
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# Object.keys 함수(JavaScript)
개체의 열거 가능한 속성 및 메서드 이름을 반환합니다.  
  
## 구문  
  
```javascript  
Object.keys(object)  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`object`|필수 요소.  속성과 메서드가 포함된 개체입니다.  사용자가 만든 개체나 기존 DOM\(문서 개체 모델\) 개체일 수 있습니다.|  
  
## 반환 값  
 개체의 열거 가능 속성과 메서드 이름이 포함된 배열입니다.  
  
## 예외  
 `object` 인수에 대해 제공된 값이 개체의 이름이 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## 설명  
 `keys` 메서드는 열거 가능 속성과 메서드 이름만 반환합니다.  열거 가능 및 열거 불가능 속성과 메서드의 이름을 모두 반환하려면 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)를 사용할 수 있습니다.  
  
 속성의 `enumerable` 특성에 대한 자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md) 및 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 세 개의 속성과 한 개의 메서드가 포함된 개체를 만듭니다.  `keys` 메서드를 사용하여 개체의 속성과 메서드를 가져옵니다.  
  
```javascript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
  
    // Define a method.  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Put the enumerable properties and methods of the object in an array.  
var arr = Object.keys(spaghetti);  
document.write (arr);  
  
// Output:  
// grain,width,shape,toString  
```  
  
## 예제  
 다음 예제에서는 Pasta 개체에서 "g" 문자로 시작하는 모든 열거 가능 속성의 이름을 표시합니다.  
  
```javascript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
}  
  
var polenta = new Pasta("corn", 1, "mush");  
  
var keys = Object.keys(polenta).filter(CheckKey);  
document.write(keys);  
  
// Check whether the first character of a string is "g".  
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);  
    if (firstChar.toLowerCase() == "g")  
        return true;  
    else  
        return false;  
}  
  
// Output:  
// grain  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)