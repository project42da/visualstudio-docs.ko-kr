---
title: "&#39;Finally&#39;는 &#39;Try&#39; 문 외부에 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30382"
  - "bc30382"
helpviewer_keywords: 
  - "BC30382"
ms.assetid: 0314d8d2-18bc-4bbd-858c-0a18408b52fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Finally&#39;는 &#39;Try&#39; 문 외부에 사용할 수 없습니다.
`Finally`는 `Try...Catch...Finally` 블록을 완료하는 데 사용되므로 블록의 끝에 한 번만 나타날 수 있습니다. 불필요한 `Finally`가 있거나, `Finally` 문이 해당 `Try` 블록의 경계 외부에 나타납니다.  
  
 **오류 ID:** BC30382  
  
### 이 오류를 해결하려면  
  
1.  불필요한 `Finally`문을 찾아서 제거합니다.  
  
2.  `Finally` 문을 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)