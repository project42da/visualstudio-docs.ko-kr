---
title: "컴파일러 오류 CS0525 | Microsoft Docs"
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
  - "CS0525"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0525"
ms.assetid: fcecfd4f-221f-41e6-a95c-1685be78926e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0525
인터페이스는 필드를 포함할 수 없습니다.  
  
 [interface](/dotnet/csharp/language-reference/keywords/interface)에 메서드 및 속성이 포함될 수 있지만 필드는 포함되지 않습니다.  
  
 다음 샘플에서는 CS0525를 생성합니다.  
  
```  
// CS0525.cs namespace x { public interface clx { public int i;   // CS0525 } }  
```