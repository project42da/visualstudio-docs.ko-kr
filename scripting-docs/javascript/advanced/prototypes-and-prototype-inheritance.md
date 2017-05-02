---
title: "프로토타입 및 프로토타입 상속 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "프로토타입[JavaScript]"
  - "프로토타입 상속[JavaScript]"
ms.assetid: 1e1d0631-2a9f-4011-b9fe-fa338e1ef34c
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로토타입 및 프로토타입 상속
JavaScript에서 `prototype`은 함수의 속성이며 생성자 함수에서 만든 개체의 속성입니다.  함수의 프로토타입은 개체입니다.  이는 함수가 생성자로 사용될 때 주로 사용됩니다.  
  
```javascript  
function Vehicle(wheels, engine) {  
    this.wheels = wheels;  
    this.engine = engine;  
}  
```  
  
 위의 예제에서 `Vehicle` 함수의 프로토타입은 `Vehicle` 생성자로 인스턴스화된 개체의 프로토타입입니다.  
  
## Add 속성 및 메서드에 프로토타입 사용  
 `prototype` 속성을 사용하여 속성 및 메서드를 개체에 추가할 수 있으며 이미 만들어진 경우라도 추가할 수 있습니다.  
  
```javascript  
var testVehicle = new Vehicle(2, false);  
Vehicle.prototype.color = "red";  
var testColor = testVehicle.color;  
```  
  
 `testColor`의 값이 "red"입니다.  
  
 미리 정의된 개체에도 속성 및 메서드를 추가할 수 있습니다.  예를 들어, `String` 프로토타입 개체에 `Trim` 메서드를 정의할 수 있으며 스크립트의 모든 문자열이 이 메서드를 상속합니다.  
  
```javascript  
String.prototype.trim = function()  
{  
    // Replace leading and trailing spaces with the empty string  
    return this.replace(/(^\s*)|(\s*$)/g, "");  
}  
var s = "    leading and trailing spaces    ";  
// Displays "    leading and trailing spaces     (35)"  
window.alert(s + " (" + s.length + ")");  
// Remove the leading and trailing spaces  
s = s.trim();  
// Displays "leading and trailing spaces (27)"  
window.alert(s + " (" + s.length + ")");  
```  
  
### Object.create를 사용하여 다른 개체에서 한 개체를 파생하기 위해 프로토타입 사용  
 `prototype` 개체를 사용하여 다른 개체에서 한 개체를 파생할 수 있습니다.  예를 들어, [Object.create](../../javascript/reference/object-create-function-javascript.md) 함수를 사용하여 이전에 정의한 `Vehicle` 개체의 프로토타입을 사용하는 새 개체 `Bicycle`을 파생할 수 있습니다\(필요한 새 속성도 포함\).  
  
```javascript  
var Bicycle = Object.create(Object.getPrototypeOf(Vehicle), {  
    "pedals" :{value: true}  
});  
  
```  
  
 `Bicycle` 개체에는 `wheels`, `engine`, `color` 및 `pedals` 속성이 있고, 그 프로토타입은 `Vehicle.prototype`입니다.  JavaScript 엔진은 `Bicycle`의 `pedals` 속성을 찾고, `Vehicle`의 `wheels`, `engine` 및 `color` 속성을 찾기 위해 프로토타입 체인을 조회합니다.  
  
### 개체의 프로토타입 변경  
 Internet Explorer 11에서 [\_\_proto\_\_](../../javascript/reference/proto-property-object-javascript.md) 속성을 사용하여 개체 또는 함수의 내부 프로토타입을 새 프로토타입으로 대체할 수 있습니다.  이 속성을 사용하면 프로토타입 체인의 다른 속성 및 메서드와 함께 새 프로토타입의 속성 및 메서드를 상속합니다.  
  
 다음 예제에서는 개체의 프로토타입을 변경하는 방법을 보여 줍니다.  이 예제에서는 개체의 프로토타입을 변경할 때 해당 개체의 상속된 속성을 변경하는 방법을 보여 줍니다.  
  
```javascript  
function Friend() {  
    this.demeanor = "happy";  
}  
  
function Foe() {  
    this.demeanor = "suspicious";  
}  
  
var friend = new Friend();  
var foe = new Foe();  
  
var player = new Object();  
player.__proto__ = foe;  
  
friend.ally = "Tom";  
  
if (console && console.log) {  
    console.log(player.demeanor === "happy" );      // Returns false  
    console.log(player.demeanor === "suspicious");  // Returns true  
    console.log(player.ally === "Tom");             // Returns false  
    // Turn the foe to a friend.  
    player.__proto__ = friend;  
    console.log(player.demeanor === "happy");       // Returns true  
    console.log(player.demeanor === "suspicious");  // Returns false  
    console.log(player.ally === "Tom");             // Returns true  
}  
```