---
title: "&#39;Exit Try&#39;는 &#39;Try&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "vbc30393"
  - "bc30393"
helpviewer_keywords: 
  - "BC30393"
ms.assetid: b8651df3-a32f-478c-a6d8-aa0ef584155f
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Try&#39;는 &#39;Try&#39; 문 내부에만 사용할 수 있습니다.
`Exit Try`는 `Try` 블록 문에서만 나올 수 있습니다. 중복 `Exit Try` 문이 있거나 또는 `Exit Try` 문이 해당 `Try` 블록의 경계를 벗어난 곳에 나타납니다.  
  
 **오류 ID:** BC30393  
  
### 이 오류를 해결하려면  
  
1.  불필요한 `Exit Try` 문을 찾아서 제거합니다.  
  
2.  `Exit Try` 문을 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)