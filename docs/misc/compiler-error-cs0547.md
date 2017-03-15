---
title: "컴파일러 오류 CS0547 | Microsoft Docs"
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
  - "CS0547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0547"
ms.assetid: aa80873f-deb0-4ff2-8435-92a626bb5b80
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0547
'property': 속성이나 인덱서에는 void 형식을 사용할 수 없습니다.  
  
 [void](/dotnet/csharp/language-reference/keywords/void)는 속성에 대한 반환 값으로 잘못되었습니다.  
  
 자세한 내용은 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)을 참조하세요.  
  
 다음 샘플에서는 CS0547을 생성합니다.  
  
```  
// CS0547.cs public class a { public void i   // CS0547 // Try the following declaration instead: // public int i { get { return 0; } } } public class b : a { public static void Main() { } }  
```