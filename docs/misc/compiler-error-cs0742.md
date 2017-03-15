---
title: "컴파일러 오류 CS0742 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0742"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0742"
ms.assetid: 078ee7af-17e4-4572-8fee-d97e09c9002b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0742
쿼리 본문은 select 절 또는 group 절로 끝나야 합니다.  
  
 쿼리 식은 연속 없이 `select` 절이나 `group` 절로 끝나야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  쿼리에 [select 절](/dotnet/csharp/language-reference/keywords/select-clause) 또는 [group 절](/dotnet/csharp/language-reference/keywords/group-clause)을 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0742를 생성합니다.  
  
```  
// cs0742.cs using System.Linq; public class Test { public static int Main() { int[] array = { 1, 2, 3 }; var query = from num in array; // CS0742 return 1; } }  
```  
  
 `group` 절이 [into](/dotnet/csharp/language-reference/keywords/into) 키워드를 사용하여 그룹화 결과를 임시 식별자에 저장하는 경우 쿼리의 마지막 절로 사용할 수 없습니다.`select` 또는 두 번째 `group` 절이 필요합니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)