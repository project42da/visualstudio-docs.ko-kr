---
title: "컴파일러 오류 CS0745 | Microsoft Docs"
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
  - "CS0745"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0745"
ms.assetid: 6ae77eb2-a940-43aa-a198-3042d144613a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0745
키워드 'by'가 필요합니다.  
  
 `group` 절에 대한 패턴은 다음 예제와 같이 `group...by` 뒤에 선택적 `into`가 오는 것입니다.  
  
```  
string[] names = { "Bob", "Bill", "Jonetta", "Mary" }; var query = from name in names group name by name[0];  
```  
  
 또는  
  
```  
var query2 = from name in names group name by name[0] into g //...additional query clauses  
```  
  
### 이 오류를 해결하려면  
  
1.  `group` 절에 `by` 키워드를 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0745를 생성합니다.  
  
```  
// cs0745.cs using System; using System.Linq; public class C { public static int Main() { string[] names = { "Bob", "Bill", "Jonetta", "Mary" }; var query = from name in names group name name[0]; // CS0745 return 1; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)   
 [group 절](/dotnet/csharp/language-reference/keywords/group-clause)