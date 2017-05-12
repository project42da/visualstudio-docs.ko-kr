---
title: "has 메서드(WeakMap)(JavaScript) | Microsoft Docs"
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
ms.assetid: 12bedca1-bde7-413a-a4e2-06c03559044f
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# has 메서드(WeakMap)(JavaScript)
`WeakMap` 개체에 지정된 요소가 들어 있는 경우 `true`를 반환합니다.  
  
## 구문  
  
```javascript  
weakmapObj.has(key)  
```  
  
#### 매개 변수  
 `weakmapObj`  
 필수 요소.  `WeakMap` 개체  
  
 `key`  
 필수 요소.  테스트할 요소의 키입니다.  
  
## 속성 값\/반환 값  
 `WeakMap`이 지정한 키를 포함하는 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `WeakMap`에 멤버를 추가한 다음`has`를 사용해 그것이 존재하는지 확인하는 방법을 보여 줍니다.  
  
```javascript  
var dog = {  
    breed: "yorkie"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
  
document.write(wm.has(dog));  
  
// Output:  
// true  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]