---
title: "런타임에 바인딩 작업은 식 트리로 변환할 수 없습니다. | Microsoft Docs"
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
  - "vbc36604"
  - "bc36604"
helpviewer_keywords: 
  - "BC36604"
ms.assetid: 6fd66d12-8c99-46e0-9095-fe1b29fd2692
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 런타임에 바인딩 작업은 식 트리로 변환할 수 없습니다.
런타임에 바인딩 작업을 식 트리로 변환하려고 했습니다. 이는 잘못된 것입니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
Option Strict Off Module Module1 Sub Main() '' Not valid. ' Test(Function(someInstance) someInstance.SomeProperty) End Sub Sub Test(ByVal ex As Expressions.Expression(Of Func(Of Object, Object))) End Sub End Module  
```  
  
 **오류 ID:** BC36604  
  
## 참고 항목  
 [Early and Late Binding](/dotnet/visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding)   
 [빌드에 없음: LINQ의 식 트리](http://msdn.microsoft.com/ko-kr/1a2e8e74-4bbc-45ab-9a46-2b6cfce3bcb2)