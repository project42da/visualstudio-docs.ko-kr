---
title: "컴파일러 오류 CS1599 | Microsoft Docs"
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
  - "CS1599"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1599"
ms.assetid: 4cdb282d-0f5d-459b-afc1-8980fbb22067
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1599
메서드 또는 대리자는 'type' 형식을 반환할 수 없습니다.  
  
 .NET Framework 클래스 라이브러리의 일부 형식\(예: <xref:System.TypedReference>, <xref:System.RuntimeArgumentHandle> 및 <xref:System.ArgIterator>\)은 잠재적으로 안전하지 않은 작업을 수행하는 데 사용될 수 있기 때문에 반환 형식으로 사용할 수 없습니다.  
  
 다음 샘플에서는 CS1599를 생성합니다.  
  
```  
// CS1599.cs using System; class MyClass { public static void Main() { } public TypedReference Test1()   // CS1599 { return null; } public ArgIterator Test2()   // CS1599 { return null; } }  
```