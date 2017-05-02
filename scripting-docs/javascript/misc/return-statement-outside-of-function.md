---
title: "함수 외부에 &#39;return&#39; 문이 있습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1018"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 함수 외부에 &#39;return&#39; 문이 있습니다.
코드의 전역 범위에서 `return` 문을 사용했습니다.  `return` 문은 함수의 본문 내에서만 표시되어야 합니다.  
  
 `()` 연산자를 사용하여 함수를 호출하는 것은 식입니다.  모든 식에는 값이 있으며 `return` 문은 함수에서 반환한 값을 지정하는 데 사용됩니다.  일반적인 형식은 다음과 같습니다.  
  
```  
  
return [ expression ];  
```  
  
 `return` 문이 실행되면 *expression*이 평가되며 함수의 값으로 반환됩니다.  식이 없으면 **undefined** 가 반환됩니다.  
  
 `return` 문이 실행될 때, 함수 본문에 아직 다른 문이 남아 있더라도 함수 실행이 중단됩니다.  이 규칙의 예외는 **return** 문이 **try** 블록 내에서 발생하고 해당 **finally** 블록이 있는 경우입니다. **finally** 블록의 코드는 함수가 반환되기 전에 실행될 것입니다.  
  
 함수가 반환되면 `return` 문을 실행하지 않고 함수 본문의 끝에 도달하기 때문에 반환된 값은 **undefined** 값입니다. 즉, 함수 결과를 더 큰 식의 일부로 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   코드의 본문\(전역 범위\)에서 `return` 문을 제거합니다.  
  
## 참고 항목  
 [return 문](../../javascript/reference/return-statement-javascript.md)   
 [Function 개체](../../javascript/reference/function-object-javascript.md)   
 [caller 속성\(Function\)](../../javascript/reference/caller-property-function-javascript.md)