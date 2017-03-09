---
title: "컴파일러 오류 CS0698 | Microsoft Docs"
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
  - "CS0698"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0698"
ms.assetid: 68211652-fdfa-4d37-9451-f0b4238f9fe6
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0698
'class'는 특성 클래스이므로 제네릭 형식을 파생시킬 수 없습니다.  
  
 특성 클래스에서 파생되는 모든 클래스는 특성입니다. 특성은 제네릭 형식이 될 수 없습니다.  
  
 다음 샘플에서는 CS0698을 생성합니다.  
  
```  
// CS0698.cs class C<T> : System.Attribute  // CS0698 { }  
```