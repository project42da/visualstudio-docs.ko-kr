---
title: "컴파일러 오류 CS0522 | Microsoft Docs"
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
  - "CS0522"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0522"
ms.assetid: f749f21e-92ee-495c-9b53-179ce9342d05
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0522
'constructor': 구조체는 기본 클래스 생성자를 호출할 수 없습니다.  
  
 [구조체](/dotnet/csharp/language-reference/keywords/struct)는 기본 클래스 생성자를 호출할 수 없습니다. 기본 클래스 생성자에 대한 호출을 제거합니다.  
  
 다음 샘플에서는 CS0522를 생성합니다.  
  
```  
// CS0522.cs public class clx { public clx(int i) { } public static void Main() { } } public struct cly { public cly(int i):base(0)   // CS0522 // try the following line instead // public cly(int i) { } }  
```