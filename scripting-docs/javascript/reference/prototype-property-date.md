---
title: "prototype 속성(Date) | Microsoft Docs"
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
ms.assetid: 44f9c637-7da7-4833-906d-358506f32ced
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# prototype 속성(Date)
날짜의 프로토타입에 대한 참조를 반환합니다.  
  
## 구문  
  
```  
  
date.prototype  
```  
  
## 설명  
 `date` 인수는 개체의 이름입니다.  
  
 `prototype` 속성은 날짜에 기본적인 함수 집합을 제공하기 위해 사용합니다.  개체의 새로운 인스턴스는 해당 개체에 할당된 프로토타입의 동작을 "상속"받습니다.  
  
 예를 들어 가장 큰 배열 요소의 값을 반환하는 `Date` 개체에 메서드를 추가하려면 함수를 선언하고 이를 `Date.prototype`에 추가한 후 사용합니다.  
  
```javascript  
function max( ){  
    var max = new Date();  
    max.setFullYear(2200, 01, 01);  
    return max;  
}  
Date.prototype.maxDate = max;  
var myDate = new Date();  
  
if (myDate < myDate.maxDate())  
    document.write("today isn't the max");  
else if (myDate == myDate.maxDate())  
    document.write("today is the max");   
  
// Output:  
// today isn't the max  
  
```  
  
 모든 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 내장 개체에는 읽기 전용인 `prototype` 속성이 있습니다.  해당 프로토타입에 속성 및 메서드가 추가될 수도 있지만 그 개체에 다른 프로토타입을 지정할 수는 없습니다.  그러나 사용자 정의 개체에는 새로운 프로토타입을 할당할 수 있습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]