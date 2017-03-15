---
title: "&#39;&lt;typeparametername1&gt;&#39; 형식 매개 변수의 이름이 &#39;&lt;methodname&gt;&#39; 부분 메서드(Partial Method) 선언에 정의된 해당 형식 매개 변수인 &#39;&lt;typeparametername2&gt;&#39;와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc31443"
  - "bc31443"
helpviewer_keywords: 
  - "BC31443"
ms.assetid: 27c81cc1-325e-4e86-9d00-34f81e928076
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeparametername1&gt;&#39; 형식 매개 변수의 이름이 &#39;&lt;methodname&gt;&#39; 부분 메서드(Partial Method) 선언에 정의된 해당 형식 매개 변수인 &#39;&lt;typeparametername2&gt;&#39;와 일치하지 않습니다.
하나 이상의 형식 매개 변수를 포함하는 부분 메서드\(Partial Method\)에서 형식 매개 변수의 이름은 메서드의 선언 및 메서드의 구현에서 동일해야 합니다.  
  
 예를 들어 다음 선언 및 구현으로 이 오류가 발생됩니다.  
  
```vb#  
' Definition of the partial method signature with type parameter T. Partial Private Sub OnNameChanged(Of T)() End Sub  
```  
  
```vb#  
'' Implementation of the partial method with type parameter N. 'Private Sub OnNameChanged(Of N)() '    Console.WriteLine("Name was changed to " & Me.Name) 'End Sub  
```  
  
 **오류 ID:** BC31443  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수를 검사하여 일치하지 않는 위치를 확인합니다. 이름이 동일하도록 필요한 경우 이름을 변경합니다.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)