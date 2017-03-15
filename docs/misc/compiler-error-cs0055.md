---
title: "컴파일러 오류 CS0055 | Microsoft Docs"
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
  - "CS0055"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0055"
ms.assetid: 4d98abf3-2690-4418-8fd0-50c0e67d0a4a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0055
일관성 없는 접근성: 'type' 매개 변수 형식이 'indexer' 인덱서보다 접근성이 부족합니다.  
  
 공용 구문은 공개적으로 액세스 가능한 개체를 반환해야 합니다. 자세한 내용은 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)을 참조하세요.  
  
 다음 샘플에서는 CS0055를 생성합니다.  
  
```  
// CS0055.cs class MyClass //defaults to private accessibility // try the following line instead // public class MyClass { } public class MyClass2 { public int this[MyClass myClass]   // CS0055 { get { return 0; } } } public class MyClass3 { public static void Main() { } }  
```