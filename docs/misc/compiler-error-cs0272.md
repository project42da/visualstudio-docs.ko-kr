---
title: "컴파일러 오류 CS0272 | Microsoft Docs"
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
  - "CS0272"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0272"
ms.assetid: 16a9aab6-922a-45a3-a0ef-f32e99f3950f
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0272
set 접근자에 액세스할 수 없으므로 'property\/indexer' 속성 또는 인덱서는 이 컨텍스트에서 사용할 수 없습니다.  
  
 이 오류는 `set` 접근자가 프로그램 코드에 액세스할 수 없을 때 발생합니다. 이 오류를 해결하려면 접근자의 접근성을 향상하거나 호출 위치를 변경합니다. 자세한 내용은 [접근자 액세스 가능성 제한](/dotnet/csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility)을 참조하세요.  
  
## 예제  
 다음 예제는 CS0272 오류가 발생하는 경우입니다.  
  
```  
// CS0272.cs public class MyClass { public int Property { get { return 0; } private set { } } } public class Test { static void Main() { MyClass c = new MyClass(); c.Property = 10;      // CS0272 // To resolve, remove the previous line // or use an appropriate modifier on the set accessor. } }  
```