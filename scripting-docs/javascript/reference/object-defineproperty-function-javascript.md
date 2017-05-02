---
title: "Object.defineProperty 함수(JavaScript) | Microsoft Docs"
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
  - "defineProperty 함수[JavaScript]"
  - "Object.defineProperty 함수[JavaScript]"
ms.assetid: c5d05346-940a-40c2-b12a-e8b25abc8d46
caps.latest.revision: 74
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 74
---
# Object.defineProperty 함수(JavaScript)
개체에 속성을 추가하거나 기존 속성의 특성을 수정합니다.  
  
## 구문  
  
```  
Object.defineProperty(object, propertyname, descriptor)  
```  
  
## 매개 변수  
 `object`  
 필수 요소.  속성을 추가 또는 수정할 개체입니다.  네이티브 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체\(사용자 정의 개체 또는 기본 제공 개체\) 또는 DOM 개체일 수 있습니다.  
  
 `propertyname`  
 필수 요소.  속성 이름을 포함하는 문자열입니다.  
  
 `descriptor`  
 필수 요소.  속성의 설명자입니다.  데이터 속성 또는 접근자 속성과 관련될 수 있습니다.  
  
## 반환 값  
 수정된 개체입니다.  
  
## 설명  
 `Object.defineProperty` 함수를 사용하여 다음을 수행할 수 있습니다.  
  
-   개체에 새 속성을 추가합니다.  개체에 지정된 속성 이름이 없을 때 수행됩니다.  
  
-   기존 속성의 특성을 수정합니다.  개체에 지정된 속성 이름이 있을 때 수행됩니다.  
  
 속성 정의는 데이터 속성 또는 접근자 속성의 특성을 설명하는 설명자 개체로 제공됩니다.  설명자 개체는 `Object.defineProperty` 함수의 매개 변수입니다.  
  
 개체에 여러 속성을 추가하거나 여러 기존 속성을 수정하려면 [Object.defineProperties 함수](../../javascript/reference/object-defineproperties-function-javascript.md)를 사용하면 됩니다.  
  
## 예외  
 `TypeError` 예외는 다음 조건에 해당할 경우 throw됩니다.  
  
-   `object` 인수가 개체가 아닙니다.  
  
-   개체가 [확장 가능](../../javascript/reference/object-isextensible-function-javascript.md)하지 않고 지정된 속성 이름이 없습니다.  
  
-   `descriptor`에 `value` 또는 `writable` 특성이 있고 `get` 또는 `set` 특성이 있습니다.  
  
-   `descriptor`에 함수가 아니거나 정의되지 않은 `get` 또는 `set` 특성이 있습니다.  
  
-   지정된 속성 이름이 이미 있고, 기존 속성에 `false`의 `configurable` 특성이 있고, `descriptor`에 기존 속성의 특성과 다른 특성이 하나 이상 들어 있습니다.  그러나 기존 속성에 `false`의 `configurable` 특성과 `true`의 `writable` 특성이 있으면 `value` 또는 `writable` 특성이 다를 수 있습니다.  
  
## 데이터 속성 추가  
 다음 예제에서 `Object.defineProperty` 함수는 사용자 정의 개체에 데이터 속성을 추가합니다.  속성을 기존 DOM 개체에 추가하려면 `var = window.document` 줄의 주석 처리를 제거합니다.  
  
```javascript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property to the object.  
Object.defineProperty(obj, "newDataProperty", {  
    value: 101,  
    writable: true,  
    enumerable: true,  
    configurable: true  
});  
  
// Set the property value.  
obj.newDataProperty = 102;  
document.write("Property value: " + obj.newDataProperty + newLine);  
  
// Output:  
// Property value: 102  
```  
  
 개체 속성을 나열하려면 다음 코드를 이 예제에 추가합니다.  
  
```javascript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
  
// Output:  
//  newDataProperty: 102  
```  
  
## 데이터 속성 수정  
 개체의 속성 특성을 수정하려면 앞에 표시된 `addDataProperty` 함수에 다음 코드를 추가합니다.  `descriptor` 매개 변수에는 `writable` 특성만 포함됩니다.  기타 데이터 속성 특성은 동일하게 유지됩니다.  
  
```javascript  
// Modify the writable attribute of the property.  
Object.defineProperty(obj, "newDataProperty", { writable: false });  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output  
// writable: false  
// value: 102  
// configurable: true  
// enumerable: true  
```  
  
## 접근자 속성 추가  
 다음 예제에서 `Object.defineProperty` 함수는 사용자 정의 개체에 접근자 속성을 추가합니다.  
  
```javascript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add an accessor property to the object.  
Object.defineProperty(obj, "newAccessorProperty", {  
    set: function (x) {  
        document.write("in property set accessor" + newLine);  
        this.newaccpropvalue = x;  
    },  
    get: function () {  
        document.write("in property get accessor" + newLine);  
        return this.newaccpropvalue;  
    },  
    enumerable: true,  
    configurable: true  
});  
  
// Set the property value.  
obj.newAccessorProperty = 30;  
document.write("Property value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// Property value: 30  
  
```  
  
 개체 속성을 나열하려면 다음 코드를 이 예제에 추가합니다.  
  
```javascript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
// Output:  
// in property get accessor  
// newAccessorProperty: 30  
  
```  
  
## 접근자 속성 수정  
 개체의 속성 특성을 수정하려면 앞에 표시된 코드에 다음 코드를 추가합니다.  `descriptor` 매개 변수에는 `get` 접근자 정의만 포함됩니다.  기타 속성 특성은 동일하게 유지됩니다.  
  
```javascript  
// Modify the get accessor.  
Object.defineProperty(obj, "newAccessorProperty", {  
    get: function () { return this.newaccpropvalue; }  
});  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newAccessorProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output:  
// get: function () { return this.newaccpropvalue; }  
// set: function (x) { document.write("in property set accessor" + newLine); this.newaccpropvalue = x; }  
// configurable: true  
// enumerable: true  
```  
  
## DOM 요소에서 속성 수정  
 다음 예제에서는 `Object.getOwnPropertyDescriptor` 함수를 사용하여 속성의 속성 설명자를 가져오고 수정하는 방식으로 기본 제공 DOM 속성을 사용자 지정하는 방법을 보여 줍니다.  이 예제에서는 ID가 "div"인 DIV 요소가 있어야 합니다.  
  
```javascript  
// Get the querySelector property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(Element.prototype, "querySelector");  
  
// Make the property read-only.  
descriptor.value = "query";  
descriptor.writable = false;  
// Apply the changes to the Element prototype.  
Object.defineProperty(Element.prototype, "querySelector", descriptor);  
  
// Get a DOM element from the HTML body.  
var elem = document.getElementById("div");  
  
// Attempt to change the value. This causes the revised value attribute to be called.  
elem.querySelector = "anotherQuery";  
document.write(elem.querySelector);  
  
// Output:  
// query  
  
```  
  
## 요구 사항  
 Internet Explorer 9 표준 모드 및 Internet Explorer 10 표준 모드와 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 모든 기능을 지원합니다.  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]에서는 DOM 개체를 지원하지만 사용자 정의 개체를 지원하지 않습니다.  `enumerable` 및 `configurable` 특성을 지정할 수는 있지만 사용되지 않습니다.  
  
## 참고 항목  
 [문서 개체 모델 프로토타입, 2부: 접근자\(getter\/setter\) 지원](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineProperties 함수](../../javascript/reference/object-defineproperties-function-javascript.md)   
 [Object.create 함수](../../javascript/reference/object-create-function-javascript.md)   
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)