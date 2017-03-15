---
title: "&#39;WithEvents&#39; 변수는 클래스, 인터페이스 또는 클래스 제약 조건이 있는 형식 매개 변수로만 형식화될 수 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30413"
  - "bc30413"
helpviewer_keywords: 
  - "BC30413"
ms.assetid: 11ddf207-2760-425f-b4c2-bb9fe6da36ea
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;WithEvents&#39; 변수는 클래스, 인터페이스 또는 클래스 제약 조건이 있는 형식 매개 변수로만 형식화될 수 있습니다.
`WithEvents`와 함께 구조체로 형식화된 변수를 선언했습니다. 이는 `WithEvents` 한정자의 올바른 사용이 아닙니다.  
  
 **오류 ID:** BC30413  
  
### 이 오류를 해결하려면  
  
1.  `AddHandler`를 사용하여 구조체에 정의된 이벤트를 처리합니다.  
  
## 참고 항목  
 [빌드에 없음: WithEvents 및 Handles 절](http://msdn.microsoft.com/ko-kr/072b9cf6-6298-46f1-849e-4edc1631564c)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [AddHandler Statement](/dotnet/visual-basic/language-reference/statements/addhandler-statement)