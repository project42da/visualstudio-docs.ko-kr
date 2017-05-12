---
title: "&#39;catch&#39;가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1033"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# &#39;catch&#39;가 필요합니다.
예외 처리 **try** 블록을 사용했지만 관련된 **catch** 문을 작성하지 않았습니다.  예외 처리 메커니즘에서는 실패할 수 있는 코드와 예외가 발생할 경우 실행되지 않아야 하는 코드가 **try** 블록 안에 래핑되어야 합니다.  예외는 **throw** 문을 사용하여 **try** 블록 내부에서 throw되고 하나 이상의 **catch** 문을 사용하여 **try** 블록 외부에서 catch됩니다.  
  
### 이 오류를 해결하려면  
  
-   관련된 **catch** 블록을 추가합니다.  
  
-   **catch** 블록 대신 **finally** 블록을 사용합니다.  
  
## 참고 항목  
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error 개체](../../javascript/reference/error-object-javascript.md)