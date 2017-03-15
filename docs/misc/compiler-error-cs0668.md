---
title: "컴파일러 오류 CS0668 | Microsoft Docs"
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
  - "CS0668"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0668"
ms.assetid: 7bdaa795-ce13-4284-b753-a617c1735cfa
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0668
두 인덱서의 이름이 다릅니다. IndexerName 특성은 한 형식 안의 모든 인덱서에 대해서는 같은 이름으로 사용되어야 합니다.  
  
 **IndexerName** 특성에 전달된 값은 형식의 모든 인덱서에 대해 동일해야 합니다.**IndexerName** 특성에 대한 자세한 내용은 [IndexerNameAttribute 클래스](frlrfSystemRuntimeCompilerServicesIndexerNameAttributeClassTopic)를 참조하세요.  
  
 다음 샘플에서는 CS0668을 생성합니다.  
  
```  
// CS0668.cs using System; using System.Runtime.CompilerServices; class IndexerClass { [IndexerName("IName1")] public int this [int index]   // indexer declaration { get { return index; } set { } } [IndexerName("IName2")] public int this [string s]    // CS0668, change IName2 to IName1 { get { return int.Parse(s); } set { } } void Main() { } }  
```