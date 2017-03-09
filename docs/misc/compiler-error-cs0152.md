---
title: "컴파일러 오류 CS0152 | Microsoft Docs"
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
  - "CS0152"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0152"
ms.assetid: 4915ca16-6485-4e1f-ace0-c71a7b339ba4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0152
이 switch 문에 이미 'label' 레이블이 있습니다.  
  
 [switch](/dotnet/csharp/language-reference/keywords/switch) 문에서 레이블이 반복되었습니다. 자세한 내용은 [switch](/dotnet/csharp/language-reference/keywords/switch)을 참조하세요.  
  
 다음 샘플에서는 CS0152를 생성합니다.  
  
```  
// CS0152.cs namespace MyNamespace { public class MyClass { public static void Main() { int i = 0; switch (i) { case 1: i++; return; case 1:   // CS0152, two case 1 statements i++; return; } } } }  
```