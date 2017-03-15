---
title: "다차원 배열은 식 트리로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc36603"
  - "vbc36603"
helpviewer_keywords: 
  - "BC36603"
ms.assetid: 65eefab7-c7ad-4dcd-bebf-2d16fba9f28f
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 다차원 배열은 식 트리로 변환할 수 없습니다.
대부분의 식은 식 트리로 변환할 수 있지만 다차원 배열은 변환할 수 없습니다. 예를 들어 다음 코드는 이 오류를 생성합니다.  
  
```vb#  
Module Module1 Sub Main() '' A multi-dimensional array cannot be converted. 'Dim expTree As Expressions.Expression(Of Func(Of Object)) = _ '    Function() New Integer(1, 1) {{1, 2}, {2, 3}} ' A one-dimensional array can be converted. Dim expTree2 As Expressions.Expression(Of Func(Of Object)) = _ Function() New Integer() {1, 2, 3} End Sub End Module  
```  
  
 **오류 ID:** BC36603  
  
## 참고 항목  
 [빌드에 없음: LINQ의 식 트리](http://msdn.microsoft.com/ko-kr/1a2e8e74-4bbc-45ab-9a46-2b6cfce3bcb2)   
 [방법: 식 트리를 사용하여 동적 쿼리 빌드](../Topic/How%20to:%20Use%20Expression%20Trees%20to%20Build%20Dynamic%20Queries%20\(C%23%20and%20Visual%20Basic\).md)   
 [NOTINBUILD Visual Basic의 다차원 배열](http://msdn.microsoft.com/ko-kr/d92cad25-07e2-4d79-8ea4-ab269700f5de)