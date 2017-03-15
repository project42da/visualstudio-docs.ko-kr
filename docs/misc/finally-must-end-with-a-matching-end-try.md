---
title: "&#39;Finally&#39;는 짝이 맞는 &#39;End Try&#39;로 끝나야 합니다. | Microsoft Docs"
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
  - "vbc30442"
  - "bc30442"
helpviewer_keywords: 
  - "BC30442"
ms.assetid: 36cce657-186c-4ba0-a760-abcef9529f18
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Finally&#39;는 짝이 맞는 &#39;End Try&#39;로 끝나야 합니다.
`Finally` 문이 코드에서 짝이 맞는 `End Try`문 없이 사용되었습니다.`Finally` 문은 `End Try` 문으로 완료되어야 합니다.  
  
 **오류 ID:** BC30442  
  
### 이 오류를 해결하려면  
  
1.  `Finally` 문을 제거합니다.  
  
2.  `End Try` 문을 추가하여 블록을 완료합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)