---
title: "컴파일러 오류 CS0176 | Microsoft Docs"
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
  - "CS0176"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0176"
ms.assetid: 783c13d8-5ac3-4aeb-bd63-0468cb05550d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0176
"member" 정적 멤버는 인스턴스 참조를 사용하여 액세스할 수 없습니다. 대신 유형 이름을 사용하여 한정하세요.  
  
 클래스 이름만 [정적](/dotnet/csharp/language-reference/keywords/static) 변수를 한정하는 데 사용할 수 있습니다. 인스턴스 이름은 한정자가 될 수 없습니다. 자세한 내용은 [정적 클래스 및 정적 클래스 멤버](/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members)을 참조하세요.  
  
 다음 샘플에서는 CS0176을 생성합니다.  
  
```  
// CS0176.cs public class MyClass2 { public static int num; } public class Test { public static void Main() { MyClass2 mc2 = new MyClass2(); int i = mc2.num;   // CS0176 // try the following line instead // int i = MyClass2.num; } }  
  
```