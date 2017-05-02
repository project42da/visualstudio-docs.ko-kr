---
title: "add 메서드(WeakSet)(JavaScript) | Microsoft Docs"
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
ms.assetid: d35d0287-6b33-4720-b9d7-8954c428ce4e
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# add 메서드(WeakSet)(JavaScript)
`WeakSet`에 새 요소를 추가합니다.  
  
## 구문  
  
```javascript  
weaksetObj.add(obj)  
```  
  
#### 매개 변수  
 `weaksetObj`  
 필수.  `WeakSet` 개체입니다.  
  
 `obj`  
 필수.  `WeakSet`의 새 요소입니다.  
  
## 설명  
 새 요소는 임의 값보다는 개체여야 하고 고유해야 합니다.  `WeakSet`에 고유하지 않은 요소를 추가하는 경우 이 새 요소가 컬렉션에 추가되지 않습니다.  
  
## 예제  
 다음 예제에서는 멤버를 집합에 추가하고 추가되었는지 확인하는 방법을 보여줍니다.  
  
```javascript  
var ws = new WeakSet();  
  
var str = new String("Thomas Jefferson");  
var num = new Number(1776);  
  
ws.add(str);  
ws.add(num);  
  
console.log(ws.has(str));  
console.log(ws.has(num));  
  
ws.delete(str);  
console.log(ws.has(str));  
  
// Output:  
// true  
// true  
// false  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]