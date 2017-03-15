---
title: "컴파일러 오류 CS0146 | Microsoft Docs"
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
  - "CS0146"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0146"
ms.assetid: 2be796e5-da2c-4939-af12-3145cd1828c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0146
'class1' 및 'class2'와 관련된 순환 기본 클래스 종속성입니다.  
  
 클래스의 상속 목록에는 자신에 대한 직접 또는 간접 참조가 포함됩니다. 클래스는 자체 클래스에서 상속할 수 없습니다. 자세한 내용은 [상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)을 참조하세요.  
  
 다음 샘플에서는 CS0146을 생성합니다.  
  
```  
// CS0146.cs namespace MyNamespace { public interface InterfaceA { } public class MyClass : InterfaceA, MyClass2 { public void Main() { } } public class MyClass2 : MyClass   // CS0146 { } }  
```