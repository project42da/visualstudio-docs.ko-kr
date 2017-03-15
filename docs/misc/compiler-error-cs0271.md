---
title: "컴파일러 오류 CS0271 | Microsoft Docs"
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
  - "CS0271"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0271"
ms.assetid: eadc9fb5-7770-4ec4-94f6-3c7cf37eec06
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0271
get 접근자에 액세스할 수 없으므로 'property\/indexer' 속성 또는 인덱서는 이 컨텍스트에서 사용할 수 없습니다.  
  
 이 오류는 액세스할 수 없는 `get` 접근자에 액세스하려고 할 때 발생합니다. 이 오류를 해결하려면 접근자의 접근성을 향상하거나 호출 위치를 변경합니다. 자세한 내용은 [접근자 접근성](/dotnet/csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility) 및 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)를 참조하세요.  
  
 다음 예제에서는 CS0271을 생성합니다.  
  
```  
// CS0271.cs public class MyClass { public int Property { private get { return 0; } set { } } public int Property2 { get { return 0; } set { } } } public class Test { public static void Main(string[] args) { MyClass c = new MyClass(); int a = c.Property;   // CS0271 int b = c.Property2;   // OK } }  
```