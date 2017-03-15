---
title: "컴파일러 오류 CS0715 | Microsoft Docs"
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
  - "CS0715"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0715"
ms.assetid: e3cd1e46-ccfa-4678-a2ed-69245f3558ba
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0715
'static class': 정적 클래스는 사용자 정의 연산자를 포함할 수 없습니다.  
  
 사용자 정의 연산자는 클래스의 인스턴스에서 작동합니다. 정적 클래스는 인스턴스화할 수 없으므로 연산자가 동작하도록 인스턴스를 만들 수 없습니다. 따라서 정적 클래스에 대해 사용자 정의 연산자를 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0715를 생성합니다.  
  
```  
// CS0715.cs public static class C { public static C operator+(C c)  // CS0715 { } public static void Main() { } }  
```