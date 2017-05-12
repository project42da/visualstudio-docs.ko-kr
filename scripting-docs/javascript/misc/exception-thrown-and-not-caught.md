---
title: "예외가 Throw되었지만 Catch하지 못했습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5022"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 예외가 Throw되었지만 Catch하지 못했습니다.
코드에 `throw` 문을 포함했지만 **try** 블록 내에 포함되지 않았거나 오류를 포착할 연관된 **catch** 블록이 없습니다.  **throw** 문을 사용할 때 **try** 블록 내에서 예외가 throw되고 **catch** 문을 사용할 때 **try** 블록 외에서 예외가 catch되었습니다.  
  
### 이 오류를 해결하려면  
  
-   **try** 블록에서 예외를 throw할 수 있는 코드를 포함하고 해당하는 **catch** 블록이 있는지 확인하세요.  
  
-   catch 문에 올바른 예외 형식이 예상되는지 확인하세요.  
  
-   예외가 다시 throw되면 다른 해당 catch 문이 있는지 확인하세요.  
  
## 참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)   
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)