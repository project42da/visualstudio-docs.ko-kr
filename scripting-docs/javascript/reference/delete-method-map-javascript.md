---
title: "delete 메서드(Map)(JavaScript) | Microsoft Docs"
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
ms.assetid: a073e1a1-5862-485b-b2bd-26c66a3aff51
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# delete 메서드(Map)(JavaScript)
맵에서 지정된 요소를 제거합니다.  
  
## 구문  
  
```javascript  
mapObj.delete(key)  
```  
  
#### 매개 변수  
 `mapObj`  
 필수 요소.  `Map` 개체  
  
 `key`  
 필수 요소.  제거할 요소의 키입니다.  
  
## 속성 값\/반환 값  
 요소가 제거된 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `Map`에 멤버를 추가한 다음 그 중 하나를 삭제하는 방법을 보여 줍니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.delete(1);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// red  
// 2  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]