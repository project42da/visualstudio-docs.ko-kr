---
title: "컴파일러 오류 CS1511 | Microsoft Docs"
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
  - "CS1511"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1511"
ms.assetid: c04b5268-5bc3-41db-af6b-463ab1d802b4
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1511
'base' 키워드는 정적 메서드에서 사용할 수 없습니다.  
  
 [base](/dotnet/csharp/language-reference/keywords/base) 키워드가 [정적](/dotnet/csharp/language-reference/keywords/static) 메서드에서 사용되었습니다.`base`는 인스턴스 생성자, 인스턴스 메서드 또는 인스턴스 접근자에서만 호출할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 CS1511을 생성합니다.  
  
```  
// CS1511.cs // compile with: /target:library public class A { public int j = 0; } class C : A { public void Method() { base.j = 3;   // base allowed here } public static int StaticMethod() { base.j = 3;   // CS1511 return 1; } }  
```