---
title: "컴파일러 오류 CS0101 | Microsoft Docs"
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
  - "CS0101"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0101"
ms.assetid: edb5246b-c16b-4845-bb2d-0ef769d014c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0101
'namespace' 네임스페이스에 이미 'type'에 대한 정의가 포함되어 있습니다.  
  
 [네임스페이스](/dotnet/csharp/language-reference/keywords/namespace)에 중복 식별자가 있습니다. 중복 식별자 중 하나를 삭제하거나 이름을 바꿉니다. 자세한 내용은 [네임스페이스](/dotnet/csharp/programming-guide/namespaces/index)을 참조하세요.  
  
 다음 샘플에서는 CS0101을 생성합니다.  
  
```  
// CS0101.cs namespace MyNamespace { public class MyClass { static public void Main() { } } public class MyClass   // CS0101 { } }  
```