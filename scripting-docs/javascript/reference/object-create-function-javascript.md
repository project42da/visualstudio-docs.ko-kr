---
title: "Object.create 함수(JavaScript) | Microsoft Docs"
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
  - "create 함수[JavaScript]"
  - "Object.create 함수[JavaScript]"
ms.assetid: 0ad31f36-a9ee-444e-b0fe-c87843d03196
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# Object.create 함수(JavaScript)
지정된 프로토타입을 포함하고 선택적으로 지정된 속성을 포함하는 개체를 만듭니다.  
  
## 구문  
  
```  
Object.create(prototype, descriptors)  
```  
  
#### 매개 변수  
 `prototype`  
 필수 요소.  프로토타입으로 사용할 개체입니다.  `null`일 수 있습니다.  
  
 `descriptors`  
 선택 사항입니다.  하나 이상의 속성 설명자를 포함하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
 *데이터 속성*은 값을 가져오고 설정할 수 있는 속성입니다.  데이터 속성 설명자에는 `value` 특성과 `writable`, `enumerable` 및 `configurable` 특성이 포함됩니다.  마지막 세 가지 특성이 지정되지 않은 경우 `false`가 기본값이 됩니다.  *접근자 속성*은 값을 검색하거나 설정할 때마다 사용자가 제공한 함수를 호출합니다.  접근자 속성 설명자에는 `set` 특성, `get` 특성 또는 두 특성이 모두 포함됩니다.  자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)을 참조하십시오.  
  
## 반환 값  
 지정된 내부 프로토타입을 포함하고 있으며 지정된 속성이 있는 경우 이 속성을 포함하는 새 개체입니다.  
  
## 예외  
 다음 조건 중 하나라도 true이면 `TypeError` 예외가 throw됩니다.  
  
-   `prototype` 인수는 개체가 아니며 `null`이 아닙니다.  
  
-   `descriptors` 인수의 설명자에는 `value` 또는 `writable` 특성이 있으며 `get` 또는 `set` 특성이 있습니다.  
  
-   `descriptors` 인수의 설명자에는 함수가 아닌 `get` 또는 `set` 특성이 있습니다.  
  
## 설명  
 프로토타입 체인을 중지하기 위해 `null` `prototype` 매개 변수를 사용하는 이 함수를 사용할 수 있습니다.  만든 개체에는 프로토타입이 없습니다.  
  
## 예제  
 다음 예제에서는 `null` 프로토타입을 사용하는 개체를 만들고 두 가지 열거 가능한 속성을 추가합니다.  
  
```javascript  
var newObj = Object.create(null, {  
            size: {  
                value: "large",  
                enumerable: true  
            },  
            shape: {  
                value: "round",  
                enumerable: true  
            }  
        });  
  
document.write(newObj.size + "<br/>");  
document.write(newObj.shape + "<br/>");  
document.write(Object.getPrototypeOf(newObj));  
  
// Output:  
// large  
// round  
// null  
  
```  
  
## 예제  
 다음 예제에서는 Object 개체와 같은 내부 프로토타입이 있는 개체를 만듭니다.  개체 리터럴을 사용하여 만든 개체와 같은 프로토타입이 있음을 확인할 수 있습니다.  [Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md) 함수는 원래 개체의 프로토타입을 가져옵니다.  개체의 속성 설명자를 가져오기 위해 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)를 사용할 수 있습니다.  
  
```javascript  
var firstLine = { x: undefined, y: undefined };  
  
var secondLine = Object.create(Object.prototype, {  
        x: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            },  
            y: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            }  
});  
  
document.write("first line prototype = " + Object.getPrototypeOf(firstLine));  
document.write("<br/>");  
document.write("second line prototype = " + Object.getPrototypeOf(secondLine));  
  
// Output:  
// first line prototype = [object Object]  
// second line prototype = [object Object]  
```  
  
## 예제  
 다음 예제에서는 Shape 개체와 같은 내부 프로토타입이 있는 개체를 만듭니다.  
  
```javascript  
  
// Create the shape object.  
var Shape = { twoDimensional: true, color: undefined, hasLineSegments: undefined };  
  
var Square = Object.create(Object.getPrototypeOf(Shape));  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [isPrototypeOf 메서드\(Object\)](../../javascript/reference/isprototypeof-method-object-javascript.md)   
 [개체 만들기](../../javascript/creating-objects-javascript.md)