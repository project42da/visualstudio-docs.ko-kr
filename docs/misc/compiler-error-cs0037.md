---
title: "컴파일러 오류 CS0037 | Microsoft Docs"
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
  - "CS0037"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0037"
ms.assetid: 1d34a71e-10a0-4fa8-9b94-343e69428c61
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0037
null을 허용하지 않는 값 형식이므로 null을 'type'으로 변환할 수 없습니다.  
  
 컴파일러는 값 형식에 null을 할당할 수 없습니다. null은 [참조 형식](/dotnet/csharp/language-reference/keywords/reference-types) 또는 Nullable 형식에만 할당할 수 있습니다.[struct](/dotnet/csharp/language-reference/keywords/struct)가 값 형식입니다. 자세한 내용은 [nullable 형식](/dotnet/csharp/programming-guide/nullable-types/index)을 참조하세요.  
  
 다음 샘플에서는 CS0037을 생성합니다.  
  
```  
// CS0037.cs public struct s { } class a { public static void Main() { int i = null;   // CS0037 s ss = null;    // CS0037 } }  
```