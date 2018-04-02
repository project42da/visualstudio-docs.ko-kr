---
title: 프로토타입 및 프로토타입 상속 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- prototype [JavaScript]
- prototype inheritance [JavaScript]
ms.assetid: 1e1d0631-2a9f-4011-b9fe-fa338e1ef34c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 200ca757e72b2eec8f09fd48a841cc8eb816c85d
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="prototypes-and-prototype-inheritance"></a>프로토타입 및 프로토타입 상속
JavaScript에서 `prototype`은 함수의 속성이며 생성자 함수에서 만든 개체의 속성입니다. 함수의 프로토타입은 개체입니다. 이는 함수가 생성자로 사용될 때 주로 사용됩니다.  
  
```JavaScript  
function Vehicle(wheels, engine) {  
    this.wheels = wheels;  
    this.engine = engine;  
}  
```  
  
 위의 예제에서 `Vehicle` 함수의 프로토타입은 `Vehicle` 생성자로 인스턴스화된 개체의 프로토타입입니다.  
  
## <a name="using-prototypes-to-add-properties-and-methods"></a>Add 속성 및 메서드에 프로토타입 사용  
 `prototype` 속성을 사용하여 속성 및 메서드를 개체에 추가할 수 있으며 이미 만들어진 경우라도 추가할 수 있습니다.  
  
```JavaScript  
var testVehicle = new Vehicle(2, false);  
Vehicle.prototype.color = "red";  
var testColor = testVehicle.color;  
```  
  
 `testColor`의 값이 "red"입니다.  
  
 미리 정의된 개체에도 속성 및 메서드를 추가할 수 있습니다. 예를 들어, `Trim` 프로토타입 개체에 `String` 메서드를 정의할 수 있으며 스크립트의 모든 문자열이 이 메서드를 상속합니다.  
  
```JavaScript  
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
  
### <a name="using-prototypes-to-derive-one-object-from-another-with-objectcreate"></a>Object.create를 사용하여 다른 개체에서 한 개체를 파생하기 위해 프로토타입 사용  

`Object` 프로토타입을 사용하여 다른 개체에서 한 개체를 파생할 수 있습니다. 예를 들어 [Object.create](../../javascript/reference/object-create-function-javascript.md) 함수를 사용하여 이전에 정의한 `Vehicle` 개체의 프로토타입을 사용하는 새 개체 `Bicycle`을 파생할 수 있습니다(필요한 새 속성도 포함).  
  
```JavaScript  
var bicycle = Object.create(Object.getPrototypeOf(Vehicle), {  
    "pedals" :{value: true}  
});  
  
```  
  
 `bicycle` 개체에는 `wheels`, `engine`, `color` 및 `pedals` 속성이 있고, 그 프로토타입은 `Vehicle.prototype`입니다. JavaScript 엔진은 `pedals`의 `bicycle` 속성을 찾고, `wheels`의 `engine`, `color` 및 `Vehicle` 속성을 찾기 위해 프로토타입 체인을 조회합니다.  
  
### <a name="changing-an-objects-prototype"></a>개체의 프로토타입 변경  
Internet Explorer 11에서 [__proto__](../../javascript/reference/proto-property-object-javascript.md) 속성을 사용하여 개체 또는 함수의 내부 프로토타입을 새 프로토타입으로 대체할 수 있습니다. 이 속성을 사용하면 프로토타입 체인의 다른 속성 및 메서드와 함께 새 프로토타입의 속성 및 메서드를 상속합니다.  

> [!WARNING]
> `__proto__` 속성은 레거시 기능입니다. 대신 [Object.getPrototypeOf](../reference/object-getprototypeof-function-javascript.md)를 사용합니다.
  
다음 예제에서는 개체의 프로토타입을 변경하는 방법을 보여 줍니다. 이 예제에서는 개체의 프로토타입을 변경할 때 해당 개체의 상속된 속성을 변경하는 방법을 보여 줍니다.  
  
```JavaScript  
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
