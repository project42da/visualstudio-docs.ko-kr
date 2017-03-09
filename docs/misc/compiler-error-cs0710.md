---
title: "컴파일러 오류 CS0710 | Microsoft Docs"
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
  - "CS0710"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0710"
ms.assetid: 753a1a87-f5e5-4758-a960-515069a6c7b0
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0710
정적 클래스는 인스턴스 생성자를 포함할 수 없습니다.  
  
 정적 클래스는 인스턴스화할 수 없으므로 생성자가 필요하지 않습니다. 이 오류를 방지하려면 정적 클래스에서 모든 생성자를 제거하거나, 인스턴스를 생성하려는 경우 클래스를 비정적으로 설정합니다.  
  
 다음 샘플에서는 CS0710을 생성합니다.  
  
```  
// CS0710.cs public static class C { public C()  // CS0710 { } public static void Main() { } }  
```