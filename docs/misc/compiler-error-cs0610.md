---
title: "컴파일러 오류 CS0610 | Microsoft Docs"
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
  - "CS0610"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0610"
ms.assetid: 6cdce74c-5c00-4539-9df1-32be70e9912d
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0610
필드 또는 속성은 'type' 형식일 수 없습니다.  
  
 필드 또는 속성으로 사용할 수 없는 일부 형식이 있습니다. 이러한 형식에는 **System.ArgIterator** 및 **System.TypedReference**가 포함됩니다.  
  
 다음 샘플에서는 **System.TypedReference**를 필드로 사용하며, 그 결과로 CS0610을 생성합니다.  
  
```  
// CS0610.cs public class MainClass { System.TypedReference i;   // CS0610 public static void Main () { } public static void Test(System.TypedReference i)   // OK { } }  
```