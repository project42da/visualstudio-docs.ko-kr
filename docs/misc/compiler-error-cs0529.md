---
title: "컴파일러 오류 CS0529 | Microsoft Docs"
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
  - "CS0529"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0529"
ms.assetid: 61de8086-f991-455c-b009-bb8cd05f34bd
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0529
상속된 'interface1' 인터페이스는 'interface2'의 인터페이스 계층 구조에서 순환됩니다.  
  
 [interface](/dotnet/csharp/language-reference/keywords/interface)의 상속 목록에 자신에 대한 직접 또는 간접 참조가 포함되어 있습니다. 인터페이스는 다른 인터페이스에서만 상속할 수 있습니다.  
  
 다음 샘플에서는 CS0529를 생성합니다.  
  
```  
// CS0529.cs namespace x { public interface a { } public interface b : a, c { } public interface c : b   // CS0529, b inherits from c { } }  
```