---
title: "set 메서드(Map)(JavaScript) | Microsoft Docs"
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
ms.assetid: 31ee71a0-b09d-442a-9e02-825accf94ffa
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# set 메서드(Map)(JavaScript)
맵에 새 요소를 추가합니다.  
  
## 구문  
  
```javascript  
mapObj.set(key, value)  
```  
  
#### 매개 변수  
 `mapObj`  
 필수 사항입니다.  `Map` 개체  
  
 `key`  
 필수 사항입니다.  새 요소의 키입니다.  
  
 `value`  
 필수 사항입니다.  추가할 요소의 값입니다.  
  
## 속성 값\/반환 값  
 새로운 키\/값 쌍을 포함하는 `Map` 개체를 반환합니다.  
  
## 설명  
 기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
## 예제  
 다음 예제에서는 `Map`에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// black  
// red  
// 2  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]