---
title: "&#39;&lt;methodname1&gt;&#39; 메서드에 부분 메서드(Partial Method) &#39;&lt;methodname2&gt;&#39;와 같은 제네릭 제약 조건이 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31438"
  - "vbc31438"
helpviewer_keywords: 
  - "BC31438"
ms.assetid: ea092f0c-661b-49db-80c1-76401fc8bc0b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname1&gt;&#39; 메서드에 부분 메서드(Partial Method) &#39;&lt;methodname2&gt;&#39;와 같은 제네릭 제약 조건이 없습니다.
부분 메서드\(Partial Method\) 선언의 제약 조건과 다른 제네릭 제약 조건을 가진 부분 메서드\(Partial Method\) 구현을 정의했습니다. 다음 코드에서는 오류를 보여 줍니다.  
  
```vb#  
Partial Class Class1 Partial Private Sub Test(Of T As Class)(ByVal arg As T) End Sub End Class Partial Class Class1 '' The error occurs here, for Test. 'Private Sub Test(Of T As Structure)(ByVal arg As T) 'End Sub End Class  
```  
  
 **오류 ID:** BC31438  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)   
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)