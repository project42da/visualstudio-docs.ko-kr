---
title: "컴파일러 오류 CS0575 | Microsoft Docs"
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
  - "CS0575"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0575"
ms.assetid: e8f20960-94a6-41d0-807c-d49ad198ccf6
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0575
클래스 형식만 소멸자를 포함할 수 있습니다.  
  
 [struct](/dotnet/csharp/language-reference/keywords/struct)는 소멸자를 포함할 수 없습니다.  
  
 다음 샘플에서는 CS0575를 생성합니다.  
  
```  
// CS0575.cs namespace x { public struct iii { ~iii()   // CS0575 { } public static void Main() { } } }  
```