---
title: "컴파일러 오류 CS0609 | Microsoft Docs"
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
  - "CS0609"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0609"
ms.assetid: f3ff07a6-1190-4a1c-86a5-f607e1a32b78
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0609
override로 표시된 인덱서에는 IndexerName 특성을 설정할 수 없습니다.  
  
 이름 특성\(**IndexerNameAttribute**\)을 재정의인 인덱싱된 속성에 적용할 수 없습니다. 자세한 내용은 [인덱서](/dotnet/csharp/programming-guide/indexers/index)를 참조하세요.  
  
 다음 샘플에서는 CS0609를 생성합니다.  
  
```  
// CS0609.cs using System; using System.Runtime.CompilerServices; public class idx { public virtual int this[int iPropIndex] { get { return 0; } set { } } } public class MonthDays : idx { [IndexerName("MonthInfoIndexer")]   // CS0609, delete to resolve this CS0609 public override int this[int iPropIndex] { get { return 0; } set { } } } public class test { public static void Main( string[] args ) { } }  
```