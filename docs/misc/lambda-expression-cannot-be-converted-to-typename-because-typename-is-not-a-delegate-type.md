---
title: "&#39;&lt;typename&gt;&#39;이 대리자 형식이 아니므로 람다 식을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc36625"
  - "vbc36625"
helpviewer_keywords: 
  - "BC36625"
ms.assetid: c03634d4-d831-4f8c-b6ab-566465968e4d
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;이 대리자 형식이 아니므로 람다 식을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다.
람다 식은 대리자가 유효한 위치에서 사용할 수 있습니다. 호환되는 대리자 형식으로 변환할 수 있지만 다른 형식으로는 변환할 수 없습니다. 예를 들어 대리자 형식을 정의한 다음 여기에 람다 식을 할당하거나, 람다 식을 인수로 <xref:System.Func%601> 매개 변수에 보낼 수 있습니다. 이러한 예제가 다음 코드에 표시됩니다.  
  
```vb#  
Module Module1 Delegate Function FunDel(ByVal m As Integer) As Boolean Sub Main() ' Assign a lambda expression to a function delegate. Dim negative As FunDel = Function(n As Integer) n < 0 Console.WriteLine(negative(-3)) ' Send a lambda as the argument to a delegate parameter. Dim numbers() As Integer = {3, 4, 2, 8, 1, 0, 9, 13, 42} Dim evens = numbers.Where(Function(n) n Mod 2 = 0) For Each even In evens Console.WriteLine(even) Next End Sub End Module  
```  
  
 **오류 ID:** BC36625  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)