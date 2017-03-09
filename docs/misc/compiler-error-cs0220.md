---
title: "컴파일러 오류 CS0220 | Microsoft Docs"
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
  - "CS0220"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0220"
ms.assetid: f520bf34-bff8-4796-882b-1a9b1d5b977c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0220
checked 모드에서 컴파일하면 작업이 오버플로됩니다.  
  
 작업이 기본값인 [checked](/dotnet/csharp/language-reference/keywords/checked)로 검색되어 데이터가 손실되었습니다. 이 오류를 해결하려면 할당에 대한 입력을 수정하거나 [unchecked](/dotnet/csharp/language-reference/keywords/unchecked)를 사용합니다. 자세한 내용은 [Checked 및 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)을 참조하세요.  
  
 다음 샘플에서는 CS0220을 생성합니다.  
  
```  
// CS0220.cs using System; class TestClass { const int x = 1000000; const int y = 1000000; public int MethodCh() { int z = (x * y);   // CS0220 return z; } public int MethodUnCh() { unchecked { int z = (x * y); return z; } } public static void Main() { TestClass myObject = new TestClass(); Console.WriteLine("Checked  : {0}", myObject.MethodCh()); Console.WriteLine("Unchecked: {0}", myObject.MethodUnCh()); } }  
```