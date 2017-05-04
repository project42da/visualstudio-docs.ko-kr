---
title: "__proto__ 속성(Object)(JavaScript) | Microsoft Docs"
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
  - "__proto__"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 97c3f84d-125e-4905-b921-b021264964ee
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# __proto__ 속성(Object)(JavaScript)
지정된 개체의 내부 프로토타입에 대한 참조를 포함합니다.  
  
## 구문  
  
```  
object.__proto__  
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  프로토타입을 설정할 개체입니다.  
  
## 설명  
 `__proto__` 속성을 사용하여 개체에 대한 프로토타입을 설정할 수 있습니다.  
  
 개체나 함수는 새 프로토타입의 프로토타입 체인의 모든 메서드와 속성과 함께 새 프로토타입의 메서드와 속성을 모두 상속합니다.  개체는 단일 프로토타입만 가질 수 있으므로\(프로토타입 체인에서 상속된 프로토타입은 포함하지 않음\), `__proto__` 속성을 호출하면 이전 프로토타입을 대체합니다.  
  
 단지 확장 가능한 개체에서만 프로토타입을 설정할 수 있습니다.  자세한 내용은 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)을 참조하십시오.  
  
> [!NOTE]
>  `__proto__` 속성 이름은 두 개의 밑줄로 시작하고 끝납니다.  
  
## 예제  
 다음 코드 예제에서는 개체의 속성을 설정하는 방법을 보여 줍니다.  
  
```javascript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
if (console && console.log) {  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns true  
    rec.__proto__ = Object.prototype;  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns false  
}  
```  
  
## 예제  
 다음 코드 예제에서는 속성을 프로토타입에 추가하는 방식으로 개체에 추가하는 방법을 보여 줍니다.  
  
```javascript  
var proto = { y: 2 };  
  
var obj = { x: 10 };  
obj.__proto__ = proto;  
  
proto.y = 20;  
proto.z = 40;  
  
if (console && console.log) {  
    console.log(obj.x === 10);  // Returns true  
    console.log(obj.y === 20);  // Returns true  
    console.log(obj.z === 40);  // Returns true  
}  
```  
  
## 예제  
 다음 코드 예제는 새로운 프로토타입을 설정하여 `String` 개체에 속성을 추가합니다.  
  
```javascript  
var stringProp = { desc: "description" };  
  
String.__proto__ = stringProp;  
var s1 = "333";  
var s2 = new String("333");  
  
if (console && console.log) {  
  
    console.log(String.desc === "description"); // Returns true  
    console.log(s1.desc === "description");     // Returns false  
    console.log(s2.desc === "description");     // Returns false  
  
    s1.__proto__ = String;  // Can't be set.  
    s2.__proto__ = String;  
  
    console.log(s1.desc === "description"); // Returns false  
    console.log(s2.desc === "description"); // Returns true  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [프로토타입 및 프로토타입 상속](../../javascript/advanced/prototypes-and-prototype-inheritance.md)