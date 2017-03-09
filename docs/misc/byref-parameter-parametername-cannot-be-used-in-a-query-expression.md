---
title: "쿼리 식에는 &#39;ByRef&#39; 매개 변수 &lt;parametername&gt;을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36533"
  - "bc36533"
helpviewer_keywords: 
  - "BC36533"
ms.assetid: 8067ac87-dd6b-4869-87d0-8a4ce272de41
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 쿼리 식에는 &#39;ByRef&#39; 매개 변수 &lt;parametername&gt;을 사용할 수 없습니다.
LINQ 쿼리에 포함된 매개 변수가 포인터 형식입니다. 쿼리 식에 사용된 매개 변수는 참조로 전달할 수 없습니다.  
  
 **오류 ID:** BC36533  
  
### 이 오류를 해결하려면  
  
1.  새 변수를 선언하고 참조로 전달된 값의 복사본에 새 변수의 값을 할당합니다. LINQ 쿼리에 복사한 변수를 사용합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Sub RunQuery(ByVal collection As List(Of Integer), _  
                 ByRef filterValue As Integer)  
        Dim fv = filterValue  
        Dim queryResult = From num In collection _  
                          Where num < fv  
    End Sub  
    ```  
  
### 이 오류를 해결하려면  
  
1.  쿼리에 사용된 매개 변수에 대해 `ByRef` 키워드를 `ByVal` 키워드로 바꿉니다.  
  
## 참고 항목  
 [Differences Between Passing an Argument By Value and By Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)