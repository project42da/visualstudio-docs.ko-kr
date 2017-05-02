---
title: "isPrototypeOf 메서드(Object)(JavaScript) | Microsoft Docs"
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
  - "isPrototypeOf"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "isPrototypeOf 메서드"
ms.assetid: 9c821319-c208-480f-915e-565ef6e017b6
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# isPrototypeOf 메서드(Object)(JavaScript)
개체가 다른 개체의 프로토타입 체인에 있는지 여부를 확인합니다.  
  
## 구문  
  
```  
  
prototype.isPrototypeOf(object)  
```  
  
## 매개 변수  
 `prototype`  
 필수입니다.  개체 프로토타입  
  
 `object`  
 필수입니다.  프로토타입 체인을 확인할 또 다른 개체입니다.  
  
## 설명  
 `object`의 프로토타입 체인에 `prototype`이 포함된 경우 `isPrototypeOf` 메서드가 `true`를 반환합니다.  프로토타입 체인은 동일한 유형의 개체 인스턴스 사이에 기능을 공유할 때 사용합니다.  `object`가 개체가 아니거나 `prototype`이 `object`의 프로토타입 체인에 표시되지 않으면 `isPrototypeOf` 메서드가 `false`를 반환합니다.  
  
## 예제  
 다음 예제에서는 `isPrototypeOf` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
document.write(Rectangle.prototype.isPrototypeOf(rec));  
  
// Output: true  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)