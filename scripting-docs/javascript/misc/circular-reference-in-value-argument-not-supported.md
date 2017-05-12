---
title: "값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5034"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다.
유효하지 않은 값을 사용하여 `JSON.stringify`를 호출하려고 했습니다.  `value` 인수, 배열 또는 개체는 순환 참조를 포함합니다.  
  
### 이 오류를 해결하려면  
  
-   인수에서 순환 참조를 제거하세요.  
  
## 예제  
 이 예제의 코드는 `john`에 `mary`에 대한 참조가 포함되고 `mary`에 `john`에 대한 참조가 포함되기 때문에 런타임 오류를 일으킵니다.  순환 참조를 제거하려면 `mary` 개체의 속성 `brother` 또는 `john` 개체의 `sister` 속성을 제거하거나 설정 해제합니다.  
  
```javascript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## 참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)