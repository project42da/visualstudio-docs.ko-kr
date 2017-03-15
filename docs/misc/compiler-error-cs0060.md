---
title: "컴파일러 오류 CS0060 | Microsoft Docs"
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
  - "CS0060"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0060"
ms.assetid: ae6d4fb7-5ff9-4883-82c3-f55b190f439a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0060
일관성 없는 접근성: 'class1' 기본 클래스가 'class2' 클래스보다 액세스하기 어렵습니다.  
  
 클래스의 접근성은 기본 클래스와 상속된 클래스 간에 일치해야 합니다.  
  
 다음 샘플에서는 CS0060을 생성합니다.  
  
```  
// CS0060.cs class MyClass // try the following line instead // public class MyClass { } public class MyClass2 : MyClass   // CS0060 { public static void Main() { } }  
```  
  
## 참고 항목  
 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)