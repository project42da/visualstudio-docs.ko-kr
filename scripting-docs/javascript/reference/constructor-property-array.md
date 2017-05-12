---
title: "constructor 속성(Array) | Microsoft Docs"
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
ms.assetid: b78d517b-cb56-4866-b30f-ef8121a27843
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# constructor 속성(Array)
배열을 만드는 함수를 지정합니다.  
  
## 구문  
  
```  
  
array.constructor  
```  
  
## 설명  
 필수 `array`는 배열의 이름입니다.  
  
 `constructor` 속성은 초기 설정을 가지는 모든 초기 설정 개체의 멤버입니다.  여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체가 포함됩니다.  `constructor` 속성은 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 예제  
 다음 예제에서는 constructor 속성을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var x = new Array();  
  
if (x.constructor == Array)  
    document.write("Object is an Array.");  
else  
    document.write("Object is not an Array.");  
  
// Output:  
// Object is an Array.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]