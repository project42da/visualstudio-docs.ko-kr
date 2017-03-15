---
title: "컴파일러 오류 CS0641 | Microsoft Docs"
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
  - "CS0641"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0641"
ms.assetid: 5bcdb11a-fefd-4c71-9b31-4c4f719633f3
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0641
'attribute': 특성은 System.Attribute에서 파생된 클래스에만 사용할 수 있습니다.  
  
 **System.Attribute**에서 파생된 클래스에서만 사용될 수 있는 특성이 사용되었습니다.  
  
 다음 샘플에서는 CS0641을 생성합니다.  
  
```  
// CS0641.cs using System; [AttributeUsage(AttributeTargets.All)] public class NonAttrClass   // CS0641 // try the following line instead // public class NonAttrClass : Attribute { } class MyClass { public static void Main() { } }  
```