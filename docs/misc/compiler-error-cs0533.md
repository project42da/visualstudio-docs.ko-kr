---
title: "컴파일러 오류 CS0533 | Microsoft Docs"
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
  - "CS0533"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0533"
ms.assetid: f8b38c5a-d365-4081-a101-6282bdd19069
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0533
'derived\-class member'가 상속된 추상 멤버 'base\-class member'를 숨깁니다.  
  
 기본 [class](/dotnet/csharp/language-reference/keywords/class) 메서드가 숨겨집니다. 선언의 구문을 확인하여 올바른지 확인합니다.  
  
 자세한 내용은 [base](/dotnet/csharp/language-reference/keywords/base)를 참조하세요.  
  
 다음 샘플에서는 CS0533을 생성합니다.  
  
```  
// CS0533.cs namespace x { abstract public class a { abstract public void f(); } abstract public class b : a { new abstract public void f();   // CS0533 // try the following lines instead // override public void f() // { // } public static void Main() { } } }  
```