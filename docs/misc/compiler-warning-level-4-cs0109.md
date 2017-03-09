---
title: "컴파일러 경고(수준 4) CS0109 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0109"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0109"
ms.assetid: 42ac72e5-5081-4e8b-b2cf-5e10c1606676
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS0109
'member' 멤버는 상속된 멤버를 숨기지 않으므로 new 키워드가 필요하지 않습니다.  
  
 선언에서 기본 클래스의 기존 선언을 재정의하지 않는데 클래스 선언에 [new](/dotnet/csharp/language-reference/keywords/new) 키워드가 포함되었습니다.**new** 키워드를 삭제할 수 있습니다.  
  
 다음 샘플에서는 CS0109를 생성합니다.  
  
```  
// CS0109.cs // compile with: /W:4 namespace x { public class a { public int i; } public class b : a { public new int i; public new int j;   // CS0109 public static void Main() { } } }  
```