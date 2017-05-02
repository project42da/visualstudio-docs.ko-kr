---
title: "delete 메서드(WeakSet)(JavaScript) | Microsoft Docs"
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
ms.assetid: 19e93366-7d42-4abf-b7b9-fcf943fa17a3
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# delete 메서드(WeakSet)(JavaScript)
`WeakSet`에서 지정된 요소를 제거합니다.  
  
## 구문  
  
```javascript  
weaksetObj.delete(obj)  
```  
  
#### 매개 변수  
 `weaksetObj`  
 필수.  `WeakSet` 개체입니다.  
  
 `obj`  
 필수.  제거할 요소입니다.  
  
## 속성 값\/반환 값  
 `true` 요소가 제거된 경우.  
  
## 예제  
 다음 예제에서는 `WeakSet`의 요소를 추가 및 삭제하는 방법을 보여줍니다.  
  
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