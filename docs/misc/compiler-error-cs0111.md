---
title: "컴파일러 오류 CS0111 | Microsoft Docs"
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
  - "CS0111"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0111"
ms.assetid: 87afb689-f27b-451d-84eb-d6bdf17aea41
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0111
'class' 형식은 동일한 매개 변수 형식을 가진 'member' 멤버를 미리 정의합니다.  
  
 CS0111은 클래스에 동일한 이름 및 매개 변수 형식을 사용하는 두 개의 멤버 선언이 포함된 경우에 발생합니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0111을 생성합니다.  
  
```  
// CS0111.cs class A { void Test() { } public static void Test(){}   // CS0111 public static void Main() {} }  
```