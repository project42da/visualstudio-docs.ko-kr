---
title: "컴파일러 오류 CS0621 | Microsoft Docs"
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
  - "CS0621"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0621"
ms.assetid: 7ff392c6-478c-4971-93dc-f837b1b8748c
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0621
'member': 가상 또는 추상 멤버는 전용일 수 없습니다.  
  
 전용 **가상** 또는 **추상** 멤버는 허용되지 않습니다.  
  
 다음 샘플에서는 CS0621을 생성합니다.  
  
```  
// CS0621.cs abstract class MyClass { private virtual void DoNothing1()   // CS0621 { } private abstract void DoNothing2();   // CS0621 public static void Main() { } }  
```