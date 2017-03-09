---
title: "컴파일러 오류 CS0140 | Microsoft Docs"
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
  - "CS0140"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0140"
ms.assetid: 61787b8a-7b69-41c1-8ee3-87f619698594
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0140
'label' 레이블이 중복되었습니다.  
  
 이름이 같은 레이블이 두 번 표시되었습니다. 자세한 내용은 [goto](/dotnet/csharp/language-reference/keywords/goto)을 참조하세요.  
  
 다음 샘플에서는 CS0140을 생성합니다.  
  
```  
// CS0140.cs namespace MyNamespace { public class MyClass { public static void Main() { label1: int i = 0; label1: int j = 0;   // CS0140, comment this line to resolve goto label1; } } }  
```