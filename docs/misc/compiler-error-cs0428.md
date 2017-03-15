---
title: "컴파일러 오류 CS0428 | Microsoft Docs"
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
  - "CS0428"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0428"
ms.assetid: 967c08f4-2761-415d-99fc-bb791d7dfc4e
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0428
'Identifier' 메서드 그룹을 비대리자 형식 'type'으로 변환할 수 없습니다.  메서드를 호출하시겠어요?  
  
 이 오류는 메서드 그룹을 비대리자 형식으로 변환하거나 괄호를 사용하지 않고 메서드를 호출하려고 할 때 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS0428을 생성합니다.  
  
```c#  
// CS0428.cs namespace ConsoleApplication1 { class Program { delegate int Del1(); delegate object Del2(); static void Main(string[] args) { ExampleClass ec = new ExampleClass(); // The following assignment statement causes compiler error CS0428. // It attempts to assign the address of Method1 to an integer variable. // You can only assign the address to an appropriate delegate type. int i = ec.Method1; // Del1 is a delegate type that is appropriate for a method like // Method1 that returns an int. The following assignment statement // does not cause an error. Del1 d1 = ec.Method1; // You can invoke Method1 and assign the int that is returned to // integer variable i. i = ec.Method1(); // The following assignment statement causes compiler error CS0428. // It attempts to assign the address of Method2 to an instance of // ExampleClass. You can only assign the address to a delegate type. ec = ExampleClass.Method2; // Del2 is a delegate type that is appropriate for a method like // Method2 that returns an instance of a class. The following assignment // statement does not cause an error. Del2 d2 = ExampleClass.Method2; // Similarly, you can invoke Method2 and assign the result returned to ec. ec = ExampleClass.Method2(); } } public class ExampleClass { public int Method1() { return 1; } public static ExampleClass Method2() { return null; } } }  
```