---
title: "&#39;End Get&#39;은 짝이 되는 &#39;Get&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30630"
  - "vbc30630"
helpviewer_keywords: 
  - "BC30630"
ms.assetid: d858076a-9088-4ad0-9766-95029476bf9b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Get&#39;은 짝이 되는 &#39;Get&#39; 뒤에 와야 합니다.
`End Get`는 `Get` 속성 프로시저를 종료하는 데 사용됩니다.`Get` 속성 프로시저 외부에서 `End Get` 구문이 발생했습니다.  
  
 **오류 ID:** BC30630  
  
### 이 오류를 해결하려면  
  
1.  `Get` 속성 프로시저가 `Property` 키워드 뒤와 `End Property` 구문 앞에서 선언되었는지 확인합니다.  
  
2.  `Get` 속성 프로시저가 `Get` 키워드로 시작하고 `End Get` 구문으로 끝나는지 확인합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Property Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/1c138efa-9bc2-44d7-80a0-f3a7c2510264)