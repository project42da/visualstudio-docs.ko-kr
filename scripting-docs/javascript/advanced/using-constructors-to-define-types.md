---
title: "생성자를 사용하여 형식 정의 | Microsoft Docs"
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
  - "생성자 함수"
  - "생성자, 만들기"
  - "개체 만들기, 생성자 함수"
  - "함수, 생성자 함수"
  - "개체, 만들기[JavaScript]"
ms.assetid: e869702e-4caf-4513-8dd5-fe690535f8aa
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 생성자를 사용하여 형식 정의
생성자는 특정 유형의 [개체](../../javascript/objects-and-arrays-javascript.md)를 인스턴스화하는 함수입니다.  **new** 키워드를 사용하여 생성자를 호출합니다.  다음은 기본 제공 JavaScript 개체와 사용자 지정 개체가 포함된 생성자의 몇 가지 예제입니다.  
  
## 생성자 예제  
  
```javascript  
// Creates a generic object.  
var myObject = new Object();  
// Creates a Date object.  
var myBirthday = new Date(1961, 5, 10);  
// Creates a user defined object.  
var myCar = new Car();  
```  
  
 생성자 함수는 새로 만든 빈 개체에 대한 참조인 **this** 키워드를 포함하며  속성을 만들고 초기 값을 지정하여 새 개체를 초기화합니다.  생성자는 생성한 개체에 대한 참조를 반환합니다.  
  
## 생성자 작성  
 **Object\(\)**, **Date\(\)** 및 **Function\(\)** 등의 미리 정의된 생성자 함수와 함께 **new** 연산자를 사용하여 개체를 만들 수 있습니다.  속성과 메서드의 집합을 정의하는 사용자 지정 생성자 함수를 만들 수도 있습니다.  다음은 사용자 지정 생성자의 예제입니다.  
  
```javascript  
function Circle (xPoint, yPoint, radius) {  
    this.x = xPoint;  // The x component of the center of the circle.  
    this.y = yPoint;  // The y component of the center of the circle.  
    this.r = radius;  // The radius of the circle.  
}  
```  
  
 Circle 생성자를 호출할 때 원의 중심점과 반경에 대한 값을 제공합니다.  세 가지 속성이 포함된 Circle 개체가 생성됩니다.  다음은 Circle 개체를 인스턴스화하는 방법입니다.  
  
```javascript  
var aCircle = new Circle(5, 11, 99);  
```  
  
 사용자 지정 생성자를 사용하여 만든 모든 개체의 형식은 `object`입니다.  JavaScript에는 `object`, `function`, `string`, `number`, `boolean` 및 `undefined`의 6가지 형식만 있습니다.  자세한 내용은 [typeof 연산자](../../javascript/reference/typeof-operator-decrementjavascript.md)를 참조하십시오.  
  
## 참고 항목  
 [bind 메서드 사용](../../javascript/advanced/using-the-bind-method-javascript.md)