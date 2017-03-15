---
title: "컴파일러 오류 CS0104 | Microsoft Docs"
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
  - "CS0104"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0104"
ms.assetid: 1a7e9ae8-308b-441b-ba85-fac974222875
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0104
'reference'는 'identifier'와 'identifier' 사이에 모호한 참조입니다.  
  
 프로그램에 두 네임스페이스에 대한 [using](/dotnet/csharp/language-reference/keywords/using) 지시문이 있고 코드에서 두 네임스페이스에 나타난 이름을 참조합니다.  
  
 다음 샘플에서는 CS0104를 생성합니다.  
  
```  
// CS0104.cs using x; using y; namespace x { public class Test { } } namespace y { public class Test { } } public class a { public static void Main() { Test test = new Test();   // CS0104, is Test in x or y namespace? // try the following line instead // y.Test test = new y.Test(); } }  
```