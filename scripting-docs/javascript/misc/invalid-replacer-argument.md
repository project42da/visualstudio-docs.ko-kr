---
title: "치환 인수가 잘못되었습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5035"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# 치환 인수가 잘못되었습니다.
유효하지 않은 인수를 사용하여 `JSON.stringify`를 호출하려고 했습니다.  `replacer` 인수는 함수 또는 배열이어야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `replacer` 인수를 함수 또는 배열로 변경하세요.  
  
## 예제  
 이 예제의 코드는 `memberfilter`가 함수 또는 배열이 아닌 개체이므로 런타임 오류를 일으킵니다.  
  
```javascript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## 참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)