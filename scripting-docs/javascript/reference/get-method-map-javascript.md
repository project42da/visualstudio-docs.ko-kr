---
title: "get 메서드(Map)(JavaScript) | Microsoft Docs"
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
ms.assetid: bebbd6bc-6e61-4674-8196-7e907798973f
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# get 메서드(Map)(JavaScript)
맵에서 지정된 요소를 반환합니다.  
  
## 구문  
  
```javascript  
mapObj.get(key)  
```  
  
#### 매개 변수  
 `mapObj`  
 필수 요소.  `Map` 개체  
  
 `key`  
 필수 요소.  `Map`에 있는 요소의 키입니다.  
  
## 속성 값\/반환 값  
 키와 연결된 개체를 반환합니다.  `Map`에 키가 포함되어 있지 않으면 이 메서드는 `undefined` 값을 반환합니다.  
  
## 예제  
 다음 예제는 `Map` 개체에서 요소를 검색하는 방법을 보여 줍니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
document.write(m.get(2));  
  
// Output:  
// red  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]