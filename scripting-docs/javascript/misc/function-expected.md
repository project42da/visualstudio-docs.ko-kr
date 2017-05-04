---
title: "함수가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT5002"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 함수가 필요합니다.
`Function` 개체가 아닌 개체에 대해 **함수 프로토타입** 메서드 중 하나를 호출하려고 했거나 함수 호출 컨텍스트에서 개체를 사용했습니다.  예를 들어 **example**이 함수가 아니기 때문에 다음 코드에서는 이 오류가 발생합니다.  
  
```javascript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### 이 오류를 해결하려면  
  
-   `Function` 개체에 대해서만 **함수 프로토타입** 메서드를 호출합니다.  
  
-   함수 호출 연산자 `()`를 사용하여 함수만 호출해야 합니다.  
  
## 참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)   
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)