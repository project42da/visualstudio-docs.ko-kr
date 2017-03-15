---
title: "컴파일러 오류 CS0107 | Microsoft Docs"
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
  - "CS0107"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0107"
ms.assetid: 505763c5-6d68-4c57-a8bd-7b03682da4c5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0107
보호 한정자가 두 개 이상 있습니다.  
  
 **internal protected**를 제외하고 하나의 액세스 한정자\([public](/dotnet/csharp/language-reference/keywords/public), [private](/dotnet/csharp/language-reference/keywords/private), [protected](/dotnet/csharp/language-reference/keywords/protected) 또는 [internal](/dotnet/csharp/language-reference/keywords/internal)\)만 클래스 멤버에 사용할 수 있습니다.  
  
 다음 샘플에서는 CS0107을 생성합니다.  
  
```  
// CS0107.cs public class C { private internal void f()   // CS0107, delete private or internal { } public static int Main() { return 1; } }  
```