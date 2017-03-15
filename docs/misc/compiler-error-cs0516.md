---
title: "컴파일러 오류 CS0516 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0516"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0516"
ms.assetid: a9de9d1d-9ee3-4533-ba31-b8cb9f9964a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0516
'constructor' 생성자는 자신을 호출할 수 없습니다.  
  
 프로그램에서 생성자를 재귀적으로 호출할 수 없습니다.  
  
 다음 샘플에서는 CS0516을 생성합니다.  
  
```  
// CS0516.cs namespace x { public class clx { public clx() : this()   // CS0516, delete "this()" { } public static void Main() { } } }  
```