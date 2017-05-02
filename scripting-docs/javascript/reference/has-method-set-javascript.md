---
title: "has 메서드(Set)(JavaScript) | Microsoft Docs"
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
ms.assetid: fb80f2e0-fc5e-4508-af14-1c3b3b833636
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# has 메서드(Set)(JavaScript)
집합이 지정된 요소를 포함하는 경우 `true`를 반환합니다.  
  
## 구문  
  
```javascript  
setObj.has(value)  
```  
  
#### 매개 변수  
 `setObj`  
 필수 요소.  `Set` 개체  
  
 `value`  
 필수 요소.  테스트할 요소입니다.  
  
## 속성 값\/반환 값  
 집합이 지정된 요소를 포함하는 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `Set`에 멤버를 추가하고, 세트가 특정 멤버를 포함하고 있는지 확인하는 방법을 보여줍니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
  
document.write(s.has(1776));  
document.write(s.has("1776"));  
  
// Output:  
// true  
// false  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]