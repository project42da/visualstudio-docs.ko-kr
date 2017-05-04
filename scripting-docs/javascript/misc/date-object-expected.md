---
title: "Date 개체가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5006"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Date 개체가 필요합니다.
`Date` 형식이 아닌 개체에 대해 **Date.prototype.toString** 또는 **Date.prototype.valueOf** 메서드를 호출하려고 했습니다.  이 호출 형식의 개체는 `Date` 형식이어야 합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### 이 오류를 해결하려면  
  
-   `Date` 형식의 개체에 대해 **Date.prototype.toString** 또는 **Date.prototype.valueOf** 메서드만 호출합니다.  
  
## 참고 항목  
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)   
 [내장 개체](../../javascript/intrinsic-objects-javascript.md)