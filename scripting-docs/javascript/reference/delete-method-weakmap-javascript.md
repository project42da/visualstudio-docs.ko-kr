---
title: "delete 메서드(WeakMap)(JavaScript) | Microsoft Docs"
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
ms.assetid: 7d54ae55-e514-45ba-b403-d1eee46837d2
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# delete 메서드(WeakMap)(JavaScript)
`WeakMap` 개체에서 지정된 요소를 제거합니다.  
  
## 구문  
  
```javascript  
weakmapObj.delete(key)  
```  
  
#### 매개 변수  
 `weakmapObj`  
 필수 요소.  `WeakMap` 개체  
  
 `key`  
 필수 요소.  제거할 요소의 키입니다.  
  
## 속성 값\/반환 값  
 요소가 제거된 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `WeakMap`에 멤버를 추가한 다음 삭제하는 방법을 보여 줍니다.  
  
```javascript  
function Dog(breed) {  
    this.breed = breed;  
}  
  
var dog = new Dog("yorkie");  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.delete(dog);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]