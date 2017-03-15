---
title: "메서드에는 &#39;On Error GoTo&#39; 문과 함께 람다 또는 쿼리 식을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36595"
  - "vbc36595"
helpviewer_keywords: 
  - "BC36595"
ms.assetid: 4e7cc11e-f53d-4481-afb4-653a81d54483
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 메서드에는 &#39;On Error GoTo&#39; 문과 함께 람다 또는 쿼리 식을 사용할 수 없습니다.
메서드에 `On Error Goto` 문과 람다 식 또는 LINQ 쿼리가 둘 다 포함되어 있습니다. 람다 식 또는 LINQ 쿼리와 함께 `On Error Goto` 문을 메서드에 포함할 수 없습니다.  
  
 **오류 ID:** BC36595  
  
### 이 오류를 해결하려면  
  
1.  `On Error Goto` 문을 사용하는 예외 처리 코드를 `Try...Catch` 문으로 바꿉니다.  
  
## 참고 항목  
 [예외 처리 소개\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/9792f16a-0cd2-40bd-ace2-f7a4344c0e52)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [On Error Statement](/dotnet/visual-basic/language-reference/statements/on-error-statement)