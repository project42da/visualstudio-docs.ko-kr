---
title: "&#39;End Try&#39;는 짝이 되는 &#39;Try&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30383"
  - "vbc30383"
helpviewer_keywords: 
  - "BC30383"
ms.assetid: 1d13357a-ab44-4082-b204-6e2e94f4774e
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Try&#39;는 짝이 되는 &#39;Try&#39; 뒤에 와야 합니다.
`End`  `Try`는 `Try` 블록을 완료하는 데 사용되므로 블록의 끝에 한 번만 나타날 수 있습니다. 중복 `End Try` 문이 있거나 `End``Try` 문이 해당 `Try` 블록의 경계 밖에 나타납니다.  
  
 **오류 ID:** BC30383  
  
### 이 오류를 해결하려면  
  
1.  불필요한 `End Try`를 찾아서 제거합니다.  
  
2.  `End Try`를 코드의 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)