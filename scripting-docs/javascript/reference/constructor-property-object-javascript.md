---
title: "constructor 속성(Object)(JavaScript) | Microsoft Docs"
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
  - "constructor"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "constructor 속성"
ms.assetid: 6f5d0e9d-e85f-4fde-b558-744510483d69
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# constructor 속성(Object)(JavaScript)
개체를 만드는 함수를 지정합니다.  
  
## 구문  
  
```  
  
object.constructor  
```  
  
## 설명  
 필수 `object`는 개체 또는 함수의 이름입니다.  
  
 `constructor` 속성은 초기 설정을 가지는 모든 초기 설정 개체의 멤버입니다.  여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체가 포함됩니다.  `constructor` 속성은 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 예제  
 다음 예제에서는 constructor 속성을 사용하는 방법을 보여 줍니다.  
  
```javascript  
// A constructor function.  
function MyObj() {  
    this.number = 1;  
}  
  
var x = new String("Hi");  
  
if (x.constructor == String)  
    document.write("Object is a String.");  
document.write ("<br />");  
  
var y = new MyObj;  
if (y.constructor == MyObj)  
    document.write("Object constructor is MyObj.");  
  
// Output:  
// Object is a String.  
// Object constructor is MyObj.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)