---
title: "Object.getOwnPropertyNames 함수(JavaScript) | Microsoft Docs"
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
  - "getOwnPropertyNames 메서드[JavaScript]"
  - "Object.getOwnPropertyNames 메서드[JavaScript]"
ms.assetid: 59f4b6b1-02be-44b3-a06c-a5ca8f70c3d8
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Object.getOwnPropertyNames 함수(JavaScript)
개체의 고유 속성 이름을 반환합니다.  개체의 고유 속성은 해당 개체에 직접 정의된 속성이며, 개체의 프로토타입으로부터 상속되지 않습니다.  개체의 속성에는 필드\(개체\) 및 함수가 모두 포함됩니다.  
  
## 구문  
  
```javascript  
Object.getOwnPropertyNames(object)  
```  
  
#### 매개 변수  
  
|매개 변수|정의|  
|-----------|--------|  
|`object`|필수 요소.  고유 속성을 포함하는 개체입니다.|  
  
## 반환 값  
 개체의 고유 속성 이름을 포함하는 배열입니다.  
  
## 예외  
 `object` 인수에 대해 제공된 값이 개체의 이름이 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## 설명  
 `getOwnPropertyNames` 메서드는 열거형 및 비열거형 속성 및 메서드의 이름을 반환합니다.  열거형 속성 및 메서드의 이름만 반환하려면 [Object.keys 함수](../../javascript/reference/object-keys-function-javascript.md)를 사용합니다.  
  
## 예제  
 다음 예제에서는 세 개의 속성과 한 개의 메서드가 포함된 개체를 만듭니다.  그 다음에는 `getOwnPropertyNames` 메서드를 사용하여 개체의 고유 속성\(메서드 포함\)을 가져옵니다.  
  
```javascript  
function Pasta(grain, width, shape) {  
    // Define properties.  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Get the own property names.  
var arr = Object.getOwnPropertyNames(spaghetti);  
document.write (arr);  
  
// Output:  
//   grain,width,shape,toString  
```  
  
## 예제  
 다음 예제에서는 Pasta 생성자로 생성된 spaghetti의 's'자로 시작하는 속성 이름을 표시합니다.  
  
```javascript  
function Pasta(grain, size, shape) {  
    this.grain = grain;   
    this.size = size;   
    this.shape = shape;   
}  
  
var spaghetti = new Pasta("wheat", 2, "circle");  
  
var names = Object.getOwnPropertyNames(spaghetti).filter(CheckKey);  
document.write(names);   
  
// Check whether the first character of a string is 's'.   
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);   
    if (firstChar.toLowerCase() == 's')  
        return true;   
    else  
         return false;   
}  
// Output:  
// size,shape  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.keys 함수](../../javascript/reference/object-keys-function-javascript.md)