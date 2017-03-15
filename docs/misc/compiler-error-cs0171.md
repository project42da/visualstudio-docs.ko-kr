---
title: "컴파일러 오류 CS0171 | Microsoft Docs"
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
  - "CS0171"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0171"
ms.assetid: 8c1d76c9-1048-4579-9031-23e3566e6288
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0171
제어를 호출자에게 반환하려면 자동으로 구현된 'name' 속성의 지원 필드가 완전히 할당되어야 합니다. 생성자 이니셜라이저에서 기본 생성자를 호출하세요.  
  
 [구조체](/dotnet/csharp/language-reference/keywords/struct)의 생성자는 구조체의 모든 필드를 초기화해야 합니다. 자세한 내용은 [생성자](/dotnet/csharp/programming-guide/classes-and-structs/constructors)을 참조하세요.  
  
 다음 샘플에서는 CS0171을 생성합니다.  
  
```  
// CS0171.cs struct MyStruct { MyStruct(int initField)   // CS0171 { // i = initField;      // uncomment this line to resolve this error } public int i; } class MyClass { public static void Main() { MyStruct aStruct = new MyStruct(); } }  
```