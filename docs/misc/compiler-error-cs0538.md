---
title: "컴파일러 오류 CS0538 | Microsoft Docs"
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
  - "CS0538"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0538"
ms.assetid: 46ac205e-16b0-4637-bd0f-9a755ac19f18
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0538
명시적 인터페이스 선언에서 'name'은 인터페이스가 아닙니다.  
  
 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)를 명시적으로 선언하려고 했지만 인터페이스가 지정되지 않았습니다.  
  
 다음 샘플에서는 CS0538을 생성합니다.  
  
```  
// CS0538.cs interface MyIFace { void F(); } public class MyClass { public void G() { } } class C: MyIFace { void MyIFace.F() { } void MyClass.G()   // CS0538, MyClass not an interface { } }  
```