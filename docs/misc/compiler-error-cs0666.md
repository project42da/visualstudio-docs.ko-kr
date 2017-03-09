---
title: "컴파일러 오류 CS0666 | Microsoft Docs"
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
  - "CS0666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0666"
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0666
'member': 구조체에 새 protected 멤버가 선언되었습니다.  
  
 [구조체](/dotnet/csharp/language-reference/keywords/struct)는 [abstract](/dotnet/csharp/language-reference/keywords/abstract)일 수 없으며 항상 암시적으로 [sealed](/dotnet/csharp/language-reference/keywords/sealed)됩니다. 구조체는 상속을 지원하지 않으므로 구조체에서 [protected](/dotnet/csharp/language-reference/keywords/protected) 멤버의 개념은 의미가 없습니다. 자세한 내용은 [상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0666을 생성합니다.  
  
```  
// CS0666.cs class M { static void Main() { } } struct S { protected int x;   // CS0666 }  
```