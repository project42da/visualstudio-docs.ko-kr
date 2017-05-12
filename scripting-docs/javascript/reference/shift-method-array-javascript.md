---
title: "shift 메서드(Array)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "shift"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "shift 메서드"
ms.assetid: f33baec5-f67e-4760-b7c1-553727bd0423
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# shift 메서드(Array)(JavaScript)
배열에서 첫 번째 요소를 제거하여 반환합니다.  
  
## 구문  
  
```  
  
arrayObj.shift( )  
```  
  
#### 매개 변수  
 필수 `arrayObj` 참조는 `Array` 개체입니다.  
  
## 반환 값  
 즉, 배열에서 제거된 요소를 반환합니다.  
  
## 설명  
 다음 예제에서는 `shift` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var arr = new Array(10, 11, 12);  
while (arr.length > 0)  
    {  
    var i = arr.shift();  
    document.write (i.toString() + " ");  
    }  
  
// Output:   
// 10 11 12  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [unshift 메서드\(Array\)](../../javascript/reference/unshift-method-array-javascript.md)