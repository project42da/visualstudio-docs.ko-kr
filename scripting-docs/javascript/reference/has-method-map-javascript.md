---
title: "has 메서드(Map)(JavaScript) | Microsoft Docs"
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
ms.assetid: 876df854-2941-4db2-92c6-1b497840b169
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# has 메서드(Map)(JavaScript)
맵이 지정된 요소를 포함하는 경우 `true`를 반환합니다.  
  
## 구문  
  
```javascript  
mapObj.has(key)  
```  
  
#### 매개 변수  
 `mapObj`  
 필수 요소.  `Map` 개체  
  
 `key`  
 필수 요소.  테스트할 요소의 키입니다.  
  
## 속성 값\/반환 값  
 맵이 지정된 요소를 포함하는 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `Map`에 멤버를 추가한 다음 지도에서 그것을 포함하고 있는지 확인하는 방법을 보여줍니다.  
  
```javascript  
var m = new Map();  
m.set(2, "red");  
  
document.write(m.has(2));  
  
// Output:  
// true  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]