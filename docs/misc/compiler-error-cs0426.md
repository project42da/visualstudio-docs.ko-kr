---
title: "컴파일러 오류 CS0426 | Microsoft Docs"
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
  - "CS0426"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0426"
ms.assetid: 62df0deb-3624-436e-9691-ebe3ee1fc31f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0426
'type' 형식에 'identifier' 형식 이름이 없습니다.  
  
 이 오류는 다른 형식 안에서 중첩된 형식을 참조하지만 그러한 중첩된 형식이 없는 경우 발생합니다. 중첩 형식의 이름을 잘못 입력하는 경우 발생할 수 있습니다. 사용한 이름의 철자를 확인하고 바깥쪽 형식에 필요한 멤버가 있는지 확인합니다.  
  
 클래스 C에 중첩된 형식 A가 없기 때문에 다음 샘플에서 CS0426을 생성합니다.  
  
```  
// CS0426.cs class C { // No nested types are declared. } class D { public static void Main() { C c = new C(); // Attempt to reference a nested type A: C.A a; // CS0426 because no such type C.A } }  
```  
  
## 참고 항목  
 [클래스 및 구조체](/dotnet/csharp/programming-guide/classes-and-structs/index)