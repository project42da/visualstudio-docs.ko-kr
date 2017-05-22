---
title: "prototype 속성(Error) | Microsoft Docs"
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
ms.assetid: 6c268a51-1a3d-4397-abf8-e54ca4e598fe
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# prototype 속성(Error)
오류의 프로토타입에 대한 참조를 반환합니다.  
  
## 구문  
  
```  
  
error.prototype  
```  
  
## 설명  
 `error` 인수는 오류의 이름입니다.  
  
 `prototype` 속성은 오류에 기본적인 기능 집합을 제공하기 위해 사용합니다.  개체의 새로운 인스턴스는 해당 개체에 할당된 프로토타입의 동작을 "상속"받습니다.  
  
 예를 들어 가장 큰 배열 요소의 값을 반환하는 `Error` 개체에 메서드를 추가하려면 함수를 선언하고 이를 `Error.prototype`에 추가한 후 사용합니다.  
  
```javascript  
function getSeverity(){  
    if (this.number > 1000)  
        return "high";  
    else  
        return "low";  
}  
Error.prototype.getSev = getSeverity;  
var myError = new Error();  
myError.number = 5000;  
  
document.write(myError.getSev());   
  
// Output: high  
  
```  
  
 모든 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 내장 개체에는 읽기 전용인 `prototype` 속성이 있습니다.  해당 프로토타입에 속성 및 메서드가 추가될 수도 있지만 그 개체에 다른 프로토타입을 지정할 수는 없습니다.  그러나 사용자 정의 개체에는 새로운 프로토타입을 할당할 수 있습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]