---
title: "Object.defineProperties 함수(JavaScript) | Microsoft Docs"
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
  - "Object.defineProperties 함수[JavaScript]"
ms.assetid: 2dae6658-a1c9-495f-bf06-bb3e964e6762
caps.latest.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 24
---
# Object.defineProperties 함수(JavaScript)
하나 이상의 속성을 개체에 추가하고\/또는 기존 속성의 특성을 수정합니다.  
  
## 구문  
  
```  
  
object.defineProperties(object, descriptors)  
```  
  
## 매개 변수  
 `object`  
 필수 요소.  속성을 추가 또는 수정할 개체입니다.  이 개체는 네이티브[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체 또는 DOM 개체일 수 있습니다.  
  
 `descriptors`  
 필수 요소.  하나 이상의 설명자 개체를 포함하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  각 설명자 개체는 데이터 속성 또는 접근자 속성을 설명합니다.  
  
## 반환 값  
 함수에 전달된 개체입니다.  
  
## 설명  
 `descriptors` 인수는 하나 이상의 설명자 개체를 포함하는 개체입니다.  
  
 *데이터 속성*은 값을 저장하고 검색할 수 있는 속성입니다.  데이터 속성 설명자에는 `value` 특성이나 `writable` 특성 또는 두 특성이 모두 포함됩니다.  자세한 내용은 [데이터 속성 및 접근자 속성](../../javascript/advanced/data-properties-and-accessor-properties.md)을 참조하십시오.  
  
 *접근자 속성*은 속성 값을 설정하거나 검색할 때마다 사용자가 제공한 함수를 호출합니다.  접근자 속성 설명자에는 `set` 특성, `get` 특성 또는 두 특성이 모두 포함됩니다.  
  
 개체에 지정된 이름을 포함하는 속성이 이미 있으면 속성 특성이 수정됩니다.  자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)을 참조하십시오.  
  
 개체를 만들거나 새 개체에 속성을 추가하려면 [Object.create 함수](../../javascript/reference/object-create-function-javascript.md)를 사용할 수 있습니다.  
  
## 속성 추가  
 다음 예제에서 `Object.defineProperties` 함수는 데이터 속성을 추가하고 접근자 속성을 사용자 정의된 개체에 추가합니다.  
  
 예제에서는 개체 리터럴을 사용해서 `newDataProperty` 및`newAccessorProperty` 설명자 개체와 함께 `descriptors` 개체를 만듭니다.  
  
```javascript  
var newLine = "<br />";  
  
var obj = {};  
Object.defineProperties(obj, {  
    newDataProperty: {  
        value: 101,  
        writable: true,  
        enumerable: true,  
        configurable: true  
    },  
    newAccessorProperty: {  
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
    }});  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
 이전 예제와 같이 다음 예제에서는 개체 리터럴을 사용하는 대신 동적으로 속성을 추가합니다.  
  
```javascript  
  
var newLine = "<br />";  
  
// Create the descriptors object.  
var descriptors = new Object();  
  
// Add a data property descriptor to the descriptors object.  
descriptors.newDataProperty = new Object();  
descriptors.newDataProperty.value = 101;  
descriptors.newDataProperty.writable = true;  
descriptors.newDataProperty.enumerable = true;  
descriptors.newDataProperty.configurable = true;  
  
// Add an accessor property descriptor to the descriptors object.  
descriptors.newAccessorProperty = new Object();  
descriptors.newAccessorProperty.set = function (x) {  
    document.write("in property set accessor" + newLine);  
    this.newaccpropvalue = x;  
};  
descriptors.newAccessorProperty.get = function () {  
    document.write("in property get accessor" + newLine);  
    return this.newaccpropvalue;  
};  
descriptors.newAccessorProperty.enumerable = true;  
descriptors.newAccessorProperty.configurable = true;  
  
// Call the Object.defineProperties function.  
var obj = new Object();  
Object.defineProperties(obj, descriptors);  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
## 속성 수정  
 개체의 속성 특성을 수정하려면 다음 코드를 추가합니다.  `Object.defineProperties` 함수는 `newDataProperty`의 `writable` 특성을 수정하고 `newAccessorProperty`의 `enumerable` 특성을 수정합니다.  속성 이름이 아직 존재하지 않기 때문에 `anotherDataProperty`를 개체에 추가합니다.  
  
```  
Object.defineProperties(obj, {  
    newDataProperty: { writable: false },  
    newAccessorProperty: { enumerable: false },  
    anotherDataProperty: { value: "abc" }  
});  
```  
  
## 요구 사항  
 Internet Explorer 9 표준, Internet Explorer 10 표준 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서 지원됩니다.  DOM 개체의 경우에만 Internet Explorer 8에서 지원되고, 그렇지 않으면 지원되지 않습니다.  
  
## 참고 항목  
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.create 함수](../../javascript/reference/object-create-function-javascript.md)   
 [Object 개체](../../javascript/reference/object-object-javascript.md)