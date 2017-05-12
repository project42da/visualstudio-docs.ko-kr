---
title: "prototype 속성(Boolean) | Microsoft Docs"
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
ms.assetid: e4f07cb5-3462-488c-a418-76064ab10eae
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# prototype 속성(Boolean)
부울의 프로토타입에 대한 참조를 반환합니다.  
  
## 구문  
  
```  
  
boolean.prototype  
```  
  
## 설명  
 `boolean` 인수는 개체 이름입니다.  
  
 `prototype` 속성은 개체 클래스에 기본 기능 집합을 제공합니다.  인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  프로토타입에 속성과 메서드를 추가할 수는 있지만 기본 제공 개체에 다른 프로토타입을 할당할 수는 없습니다.  
  
 예를 들어 배열의 최대 요소 값을 반환하는 `Boolean` 개체에 메서드를 추가하려면 함수를 선언하고 `Boolean.prototype`에 추가한 다음 사용합니다.  
  
```javascript  
function isFalse( ){  
    if (this.toString() == "false")  
         return true;  
    else  
        return false;  
}  
Boolean.prototype.isFalse = isFalse;  
var bool = new Boolean(1);  
document.write(bool.isFalse());  
  
// Output:  
// false  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]