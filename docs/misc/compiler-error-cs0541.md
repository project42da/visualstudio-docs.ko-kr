---
title: "컴파일러 오류 CS0541 | Microsoft Docs"
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
  - "CS0541"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0541"
ms.assetid: ed812c07-24f7-43c6-9a44-553f27f6249d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0541
'declaration': 명시적 인터페이스 선언은 클래스나 구조체에서만 선언할 수 있습니다.  
  
 명시적 [인터페이스](/dotnet/csharp/language-reference/keywords/interface) 선언을 [클래스](/dotnet/csharp/language-reference/keywords/class) 또는 [구조체](/dotnet/csharp/language-reference/keywords/struct) 외부에서 찾았습니다.  
  
 다음 샘플에서는 CS0541을 생성합니다.  
  
```  
// CS0541.cs namespace x { interface IFace { void F(); } interface IFace2 : IFace { void IFace.F();   // CS0541 } }  
```