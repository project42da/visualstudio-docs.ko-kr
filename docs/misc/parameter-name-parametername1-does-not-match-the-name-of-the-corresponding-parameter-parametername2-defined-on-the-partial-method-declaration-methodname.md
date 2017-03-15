---
title: "&#39;&lt;parametername1&gt;&#39; 매개 변수 이름이 &#39;&lt;methodname&gt;&#39; 부분 메서드(Partial Method) 선언에 정의된 해당 매개 변수인 &#39;&lt;parametername2&gt;&#39;와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc31442"
  - "bc31442"
helpviewer_keywords: 
  - "BC31442"
ms.assetid: 7f097bb2-071a-42ec-b7af-40da04f602f2
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;parametername1&gt;&#39; 매개 변수 이름이 &#39;&lt;methodname&gt;&#39; 부분 메서드(Partial Method) 선언에 정의된 해당 매개 변수인 &#39;&lt;parametername2&gt;&#39;와 일치하지 않습니다.
부분 메서드\(Partial Method\)의 선언 및 구현에 대해 매개 변수를 제공하는 경우 해당 매개 변수의 이름이 같아야 합니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
Partial Class Product  
  
    ' Declaration of the partial method.  
    Partial Private Sub valueChanged(ByVal newVal As Integer)  
    End Sub  
End Class  
```  
  
```vb#  
Partial Class Product  
  
    ' Implementation of the partial method. This error is  
    ' reported for parameter val.  
    ' Private Sub valueChanged(ByVal val As Integer)  
    '     MsgBox(Value was changed to " & Me.Quantity)  
    ' End Sub  
  
End Class  
```  
  
 **오류 ID:** BC31442  
  
### 이 오류를 해결하려면  
  
1.  해당 매개 변수의 이름이 같도록 선언 또는 구현에서 매개 변수 이름을 변경합니다.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)