---
title: "&#39;&lt;typename&gt;&#39; 형식은 &#39;System.Exception&#39; 또는 &#39;System.Exception&#39;에서 상속한 클래스가 아니므로 &#39;Catch&#39;로 이 형식을 catch할 수 없습니다. | Microsoft Docs"
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
  - "vbc30392"
  - "bc30392"
helpviewer_keywords: 
  - "BC30392"
ms.assetid: 1d513d1d-38f5-4b4e-95bb-9f1209553803
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 &#39;System.Exception&#39; 또는 &#39;System.Exception&#39;에서 상속한 클래스가 아니므로 &#39;Catch&#39;로 이 형식을 catch할 수 없습니다.
`Catch`는 예외를 가로챌 수만 있는데 예외에서 파생되지 않은 요소를 catch하려고 했습니다.  
  
 **오류 ID:** BC30392  
  
### 이 오류를 해결하려면  
  
1.  `Catch` 문을 제거하거나 `Catch`의 대상을 실제 예외로 변경합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 구조적 예외 처리 개요](http://msdn.microsoft.com/ko-kr/bb81af80-a735-4873-9711-6151a48e418a)