---
title: "컴파일러 오류 CS0241 | Microsoft Docs"
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
  - "CS0241"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "기본 메서드 매개 변수 값"
  - "기본값, 매개 변수 값"
  - "기본값, 메서드 매개 변수 값"
  - "기본 매개 변수 값"
  - "CS0241"
ms.assetid: be31b194-3de5-4aab-b23a-6cf790f940ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0241
기본 매개 변수 지정자가 허용되지 않습니다.  
  
 [메서드 매개 변수](/dotnet/csharp/language-reference/keywords/method-parameters)는 기본값을 가질 수 없습니다. 동일한 결과를 얻으려면 메서드 오버로드를 사용합니다. 자세한 내용은 [매개 변수 전달](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0241을 생성합니다. 또한 이 샘플에서는 기본 인수를 사용하는 메서드를 오버로드를 사용하여 시뮬레이트하는 방법을 보여 줍니다.  
  
```  
// CS0241.cs public class A { public void Test(int i = 9) {}   // CS0241 } public class B { public void Test() { Test(9); } public void Test(int i)  {} } public class C { public static void Main() { B x = new B(); x.Test(); } }  
```