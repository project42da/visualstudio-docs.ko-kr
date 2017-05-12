---
title: "get 메서드(WeakMap)(JavaScript) | Microsoft Docs"
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
ms.assetid: d922c55d-486d-4feb-aedc-1f4867c417d2
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# get 메서드(WeakMap)(JavaScript)
`WeakMap` 개체에서 지정된 요소를 반환합니다.  
  
## 구문  
  
```javascript  
weakmapObj.get(key)  
```  
  
#### 매개 변수  
 `weakmapObj`  
 필수 요소.  `WeakMap` 개체  
  
 `key`  
 필수 요소.  `WeakMap`에 있는 요소의 키입니다.  
  
## 속성 값\/반환 값  
 키와 연결된 개체를 반환합니다.  `WeakMap`에 키가 포함되어 있지 않으면 이 메서드는 `undefined` 값을 반환합니다.  
  
## 예제  
 다음 예제에서는 `WeakMap` 개체에서 멤버를 검색하는 방법을 보여 줍니다.  
  
```javascript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]