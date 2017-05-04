---
title: "add 메서드(Set)(JavaScript) | Microsoft Docs"
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
ms.assetid: b4eea447-fd5b-4380-978e-1b95f6dbc438
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# add 메서드(Set)(JavaScript)
집합에 새 요소를 추가합니다.  
  
## 구문  
  
```javascript  
setObj.add(value)  
```  
  
#### 매개 변수  
 `setObj`  
 필수 사항입니다.  `Set` 개체  
  
 `value`  
 필수 사항입니다.  `Set`의 새 요소입니다.  
  
## 설명  
 새 요소는 모든 형식이 허용되며 고유해야 합니다.  `Set`에 고유하지 않은 요소를 추가하는 경우 이 새 요소가 컬렉션에 추가되지 않습니다.  
  
## 예제  
 다음 예제에서는 집합에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]