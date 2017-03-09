---
title: "컴파일러 오류 CS0526 | Microsoft Docs"
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
  - "CS0526"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0526"
ms.assetid: befc46b4-28ea-40d3-89ac-132b92455772
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0526
인터페이스는 생성자를 포함할 수 없습니다.  
  
 생성자는 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)에 대해 정의할 수 없습니다. 메서드에 클래스와 동일한 이름이 있고 반환 형식은 없는 경우 메서드는 생성자로 간주됩니다.  
  
 다음 샘플에서는 CS0526을 생성합니다.  
  
```  
// CS0526.cs namespace x { public interface clx { public clx()   // CS0526 { } } public class cly { public static void Main() { } } }  
```