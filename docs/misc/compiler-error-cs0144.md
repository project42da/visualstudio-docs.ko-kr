---
title: "컴파일러 오류 CS0144 | Microsoft Docs"
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
  - "CS0144"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0144"
ms.assetid: 3904cab1-05bd-44ec-81d0-e36c5656f742
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0144
추상 클래스 또는 'interface' 인터페이스의 인스턴스를 만들 수 없습니다.  
  
 [추상](/dotnet/csharp/language-reference/keywords/abstract) 클래스 또는 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)의 인스턴스를 만들 수 없습니다. 자세한 내용은 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)을 참조하세요.  
  
 다음 샘플에서는 CS0144를 생성합니다.  
  
```  
// CS0144.cs interface MyInterface { } public class MyClass { public static void Main() { MyInterface myInterface = new MyInterface ();   // CS0144 } }  
```