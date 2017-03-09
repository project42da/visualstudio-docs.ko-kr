---
title: "&#39;&lt;methodname3&gt;&#39;에서 이미 부분 메서드(Partial method)를 구현했으므로 &#39;&lt;methodname1&gt;&#39; 메서드는 부분 메서드(Partial method) &#39;&lt;methodname2&gt;&#39;를 구현할 수 없습니다. | Microsoft Docs"
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
  - "vbc31434"
  - "bc31434"
helpviewer_keywords: 
  - "BC31434"
ms.assetid: 61cba19e-db11-4a06-89d6-4244d411588c
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname3&gt;&#39;에서 이미 부분 메서드(Partial method)를 구현했으므로 &#39;&lt;methodname1&gt;&#39; 메서드는 부분 메서드(Partial method) &#39;&lt;methodname2&gt;&#39;를 구현할 수 없습니다.
'\<methodname3\>'에서 이미 부분 메서드\(Partial method\)를 구현했으므로 '\<methodname1\>' 메서드는 부분 메서드\(Partial method\) '\<methodname2\>'를 구현할 수 없습니다. 하나의 메서드만 부분 메서드\(Partial method\)를 구현할 수 있습니다.  
  
 동일한 부분 메서드\(Partial method\) 선언을 구현하는 두 개의 부분 메서드\(Partial method\)를 가질 수 없습니다. 다음 코드는 이 오류를 생성합니다.  
  
```vb#  
Partial Class Product ' Declaration of the partial method. Partial Private Sub ValueChanged() End Sub End Class  
```  
  
```vb#  
Partial Class Product ' First implementation of the partial method. Private Sub ValueChanged() MsgBox(Value was changed to " & Me.Quantity) End Sub ' Second implementation of the partial method causes this error. 'Private Sub ValueChanged() '    Console.WriteLine("Quantity was changed to " & Me.Quantity) 'End Sub End Class  
```  
  
 **오류 ID:** BC31434  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)