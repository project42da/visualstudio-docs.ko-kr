---
title: "Boolean이 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5010"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Boolean이 필요합니다.
`Boolean` 이외의 형식으로 된 개체에서 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 메서드를 호출하려고 했습니다.  이 호출 형식의 개체는 `Boolean` 형식이어야 합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var o = new Object;  
o.f = Boolean.prototype.toString;  
o.f();  
```  
  
### 이 오류를 해결하려면  
  
-   **Boolean** 형식의 개체에서 Boolean**.prototype.toString** 또는 **Boolean.prototype.valueOf** 메서드만 호출하세요.  
  
## 참고 항목  
 [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)   
 [데이터 형식](../../javascript/data-types-javascript.md)   
 [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)   
 [데이터 복사, 전달 및 비교](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)