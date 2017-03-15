---
title: "&#39;?&#39; 문자는 여기에서 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36637"
  - "vbc36637"
helpviewer_keywords: 
  - "BC36637"
ms.assetid: a54c46e7-8fd8-4941-9fce-72f2b41b5e24
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;?&#39; 문자는 여기에서 사용할 수 없습니다.
'?' 문자는 nullable인 값 형식 또는 구조체를 지정하는 데 사용할 수 있습니다. 다른 상황에서의 사용은 제한됩니다. 예를 들어 다음 코드에서는 이 예외를 발생시킵니다.  
  
```  
' Not valid. ' #Const found = True?  
```  
  
 **오류 ID:** BC36637  
  
### 이 오류를 해결하려면  
  
-   선언에서 '?' 문자를 제거합니다.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)