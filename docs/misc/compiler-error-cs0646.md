---
title: "컴파일러 오류 CS0646 | Microsoft Docs"
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
  - "CS0646"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0646"
ms.assetid: 48ea306f-b4a0-4988-8d2b-ca9d38e9bdad
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0646
인덱서를 포함하는 형식에 DefaultMember 특성을 지정할 수 없습니다.  
  
 클래스 또는 다른 형식이 **System.Reflection.DefaultMemberAttribute**를 지정하는 경우 인덱서를 포함할 수 없습니다. 자세한 내용은 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)을 참조하세요.  
  
 다음 샘플에서는 CS0646을 생성합니다.  
  
```  
// CS0646.cs // compile with: /target:library [System.Reflection.DefaultMemberAttribute("x")]   // CS0646 class MyClass { public int this[int index]   // an indexer { get { return 0; } } public int x = 0; } // OK [System.Reflection.DefaultMemberAttribute("x")] class MyClass2 { public int prop { get { return 0; } } public int x = 0; } class MyClass3 { public int this[int index]   // an indexer { get { return 0; } } public int x = 0; }  
```