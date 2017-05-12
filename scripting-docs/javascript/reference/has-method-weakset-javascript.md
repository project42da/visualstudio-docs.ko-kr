---
title: "has 메서드(WeakSet)(JavaScript) | Microsoft Docs"
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
ms.assetid: e24f0876-26bd-4007-b12a-360bb6fa0951
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# has 메서드(WeakSet)(JavaScript)
`WeakSet`가 지정된 요소를 포함하는 경우 `true`를 반환합니다.  
  
## 구문  
  
```javascript  
setObj.has(obj)  
```  
  
#### 매개 변수  
 `setObj`  
 필수.  `WeakSet` 개체입니다.  
  
 `obj`  
 필수.  테스트할 요소입니다.  
  
## 속성 값\/반환 값  
 집합이 지정된 요소를 포함하는 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 멤버를 `WeakSet`에 추가한 다음 집합에 특정 멤버가 포함되는지 여부를 확인하는 방법을 보여 줍니다.  
  
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