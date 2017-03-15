---
title: "컴파일러 오류 CS0633 | Microsoft Docs"
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
  - "CS0633"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0633"
ms.assetid: a24d310b-151a-45eb-b150-3407940ec24c
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0633
'attribute' 특성에 대한 인수에는 올바른 식별자를 사용해야 합니다.  
  
 <xref:System.Diagnostics.ConditionalAttribute> 또는 <xref:System.Runtime.CompilerServices.IndexerNameAttribute> 특성에 전달하는 모든 인수는 유효한 식별자여야 합니다. 즉, 식별자에 사용할 수 없는 "\+" 등의 문자를 포함할 수 없습니다.  
  
## 예제  
 이 예제에서는 <xref:System.Diagnostics.ConditionalAttribute>를 사용하여 CS0633을 보여 줍니다. 다음 샘플에서는 CS0633을 생성합니다.  
  
```  
// CS0633a.cs #define DEBUG using System.Diagnostics; public class Test { [Conditional("DEB+UG")]   // CS0633 // try the following line instead // [Conditional("DEBUG")] public static void Main() { } }  
```  
  
## 예제  
 이 예제에서는 <xref:System.Runtime.CompilerServices.IndexerNameAttribute>를 사용하여 CS0633을 보여 줍니다.  
  
```  
// CS0633b.cs // compile with: /target:module #define DEBUG using System.Runtime.CompilerServices; public class Test { [IndexerName("Invalid+Identifier")]   // CS0633 // try the following line instead // [IndexerName("DEBUG")] public int this[int i] { get { return i; } } }  
  
```