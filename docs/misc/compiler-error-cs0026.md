---
title: "컴파일러 오류 CS0026 | Microsoft Docs"
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
  - "CS0026"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0026"
ms.assetid: 8767fbc1-8ba7-4e88-a9f9-7e620411882b
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0026
정적 속성, 정적 메서드 또는 정적 필드 이니셜라이저에는 'this' 키워드를 사용할 수 없습니다.  
  
 [this](/dotnet/csharp/language-reference/keywords/this) 키워드에서 형식 인스턴스인 개체를 참조합니다. 정적 메서드는 포함하는 클래스의 인스턴스와 독립적이므로 "this" 키워드는 의미가 없으며 허용되지 않습니다. 자세한 내용은 [정적 클래스 및 정적 클래스 멤버](/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members) 및 [개체](/dotnet/csharp/programming-guide/classes-and-structs/objects)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS0026을 생성합니다.  
  
```  
// CS0026.cs public class A { public static int i = 0; public static void Main() { // CS0026 this.i = this.i + 1; // Try the following line instead: // i = i + 1; } }  
```