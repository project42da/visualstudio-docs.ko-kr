---
title: "delete 메서드(Set)(JavaScript) | Microsoft Docs"
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
ms.assetid: 052c409e-10c9-49f2-955d-5ad7e31c14f3
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# delete 메서드(Set)(JavaScript)
집합에서 지정된 요소를 제거합니다.  
  
## 구문  
  
```javascript  
setObj.delete(value)  
```  
  
#### 매개 변수  
 `setObj`  
 필수 요소.  `Set` 개체  
  
 `value`  
 필수 요소.  제거할 요소입니다.  
  
## 속성 값\/반환 값  
 요소가 제거된 경우 `true`입니다.  
  
## 예제  
 다음 예제에서는 `Set`에 멤버를 추가한 다음 그 중 하나를 삭제하는 방법을 보여 줍니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
s.delete("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776,  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]