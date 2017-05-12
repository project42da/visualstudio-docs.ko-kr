---
title: "같은 소스 줄에서 throw 뒤에는 식이 와야 합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1035"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: b03b7747-01a1-40c6-af80-a1dd70bc5781
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 같은 소스 줄에서 throw 뒤에는 식이 와야 합니다.
`throw` 키워드를 사용했지만 동일 소스 줄의 식을 따르지 않았습니다.  `throw` 문은 `throw` 키워드와 이후 throw할 식으로 구성됩니다.  예를 들면 다음과 같습니다.  
  
```javascript  
if (denominator == 0) {  
 throw new DivideByZeroException();  
}  
```  
  
 이러한 두 구성 요소는 분할할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   `throw` 키워드 및 throw할 식이 동일한 줄에 표시되는지 확인하세요.  
  
## 참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)   
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)