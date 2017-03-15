---
title: "컴파일러 오류 CS0549 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0549"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0549"
ms.assetid: ae965019-9dee-4f28-9e9a-6f379bd0d757
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0549
'function'은 봉인 클래스 'class'의 새 가상 멤버입니다.  
  
 [sealed](/dotnet/csharp/language-reference/keywords/sealed) [클래스](/dotnet/csharp/language-reference/keywords/class)는 기본 클래스로 사용할 수 없습니다.  그러므로 봉인된 클래스에는 가상 메서드가 있어도 소용이 없습니다.  
  
 다음 샘플에서는 CS0549를 생성합니다.  
  
```  
// CS0549.cs // compile with: /target:library sealed public class MyClass { virtual public void TestMethod() {}   // CS0549 public void TestMethod2() {}   // OK }  
```