---
title: "Object.setPrototypeOf 함수(JavaScript) | Microsoft Docs"
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
ms.assetid: a2609f6e-aeee-4c13-b7cf-c31ddf58ff35
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Object.setPrototypeOf 함수(JavaScript)
개체의 프로토타입을 설정합니다.  
  
## 구문  
  
```  
Object.setPrototypeOf(obj, proto);  
```  
  
#### 매개 변수  
 `obj`  
 필수.  프로토타입을 설정하는 개체입니다.  
  
 `proto`  
 필수.  새 프로토타입 개체입니다.  
  
## 설명  
  
> [!WARNING]
>  프로토타입을 설정하면 프로토타입이 변경된 개체에 액세스할 수 있는 모든 JavaScript 코드의 성능이 저하될 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 개체의 프로토타입을 설정하는 방법을 보여 줍니다.  
  
```javascript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
if (console && console.log) {  
    console.log(Object.getPrototypeOf(rec) === Rectangle.prototype);  // Returns true  
    Object.getPrototypeOf(rec, Object.prototype);  
    console.log(Object.getPrototypeOf(rec) === Rectangle.prototype);  // Returns false  
}  
```  
  
## 예제  
 다음 코드 예제에서는 프로토타입에 속성을 추가하여 개체에 속성을 추가하는 방법을 보여 줍니다.  
  
```javascript  
var proto = { y: 2 };  
  
var obj = { x: 10 };  
Object.getPrototypeOf(obj, proto);  
  
proto.y = 20;  
proto.z = 40;  
  
if (console && console.log) {  
    console.log(obj.x === 10);  // Returns true  
    console.log(obj.y === 20);  // Returns true  
    console.log(obj.z === 40);  // Returns true  
}  
```  
  
## 예제  
 다음 코드 예제에서는 새 프로토타입을 설정하여 `String` 개체에 속성을 추가합니다.  
  
```javascript  
var stringProp = { desc: "description" };  
  
Object.getPrototypeOf(String, stringProp);  
var s1 = "333";  
var s2 = new String("333");  
  
if (console && console.log) {  
  
    console.log(String.desc === "description"); // Returns true  
    console.log(s1.desc === "description");     // Returns false  
    console.log(s2.desc === "description");     // Returns false  
  
    Object.getPrototypeOf(s1, String); // Can't be set.  
    Object.getPrototypeOf(s2, String);  
  
    console.log(s1.desc === "description"); // Returns false  
    console.log(s2.desc === "description"); // Returns true  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]