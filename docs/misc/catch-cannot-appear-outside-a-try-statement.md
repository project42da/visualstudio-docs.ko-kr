---
title: "&#39;Catch&#39;는 &#39;Try&#39; 문 외부에 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30380"
  - "vbc30380"
helpviewer_keywords: 
  - "BC30380"
ms.assetid: 73ce950d-881f-4532-8024-40a4930abd32
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Catch&#39;는 &#39;Try&#39; 문 외부에 사용할 수 없습니다.
`Catch`는 `Try...Catch...Finally` 문 블록 내에서 사용해야 합니다. 불필요한 `Catch` 문이 `Try` 블록에 있거나, `Catch` 문이 해당 `Try` 블록의 경계 외부에 나타납니다.  
  
 **오류 ID:** BC30380  
  
### 이 오류를 해결하려면  
  
1.  필요하지 않은 경우 `Catch` 문을 삭제하거나, `Try...Catch...Finally` 문 블록 내에 배치합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)