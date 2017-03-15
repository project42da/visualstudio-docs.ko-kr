---
title: "컴파일러 오류 CS0542 | Microsoft Docs"
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
  - "CS0542"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0542"
ms.assetid: 68a89948-8b56-4cd5-95e2-0df7fcad50ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0542
'user\-defined type': 멤버 이름은 바깥쪽 형식과 같을 수 없습니다.  
  
 멤버가 생성자가 아닌 경우 클래스 또는 구조체의 멤버는 클래스 또는 구조체와 동일한 이름을 가질 수 없습니다.  
  
 다음 샘플에서는 CS0542를 생성합니다.  
  
```c#  
// CS0542.cs class C { public int C; }  
```  
  
 이 오류는 실수로 생성자에 반환 형식을 입력하여 사실상 일반 메서드가 된 경우에 발생할 수 있습니다. 다음 예제에서는 반환 형식이 있어서 `F`이 생성자가 아니라 메서드이기 때문에 CS0542를 생성합니다.  
  
```c#  
// CS0542.cs class F { // Remove void from F() to resolve the problem. void F()   // CS0542, same name as the class { } } class MyClass { public static void Main() { } }  
```  
  
 클래스 이름이 'Item'이고 인덱서가 `this`로 선언된 경우 이 오류가 발생할 수 있습니다. 내보낸 코드에서 기본 인덱서에 'Item'이란 이름이 지정되므로 충돌이 발생합니다.  
  
```c#  
// CS0542b.cs class Item { public int this[int i]  // CS0542 { get { return 0; } } } class CMain { public static void Main() { } }  
```