---
title: "컴파일러 오류 CS0213 | Microsoft Docs"
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
  - "CS0213"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0213"
ms.assetid: 3c1d55e3-2b84-4c28-8206-ef65869a898c
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0213
이미 고정된 식의 주소를 가져오는 데 fixed 문을 사용할 수 없습니다.  
  
 [안전하지 않은](/dotnet/csharp/language-reference/keywords/unsafe) 메서드 또는 매개 변수의 지역 변수가 이미 스택에 고정되어 있으므로 [고정된](/dotnet/csharp/language-reference/keywords/fixed-statement) 식에서 이러한 두 변수 중 하나의 주소를 가져올 수 없습니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0213을 생성합니다.  
  
```  
// CS0213.cs // compile with: /unsafe public class MyClass { unsafe public static void Main() { int i = 45; fixed (int *j = &i) { }  // CS0213 // try the following line instead // int* j = &i; int[] a = new int[] {1,2,3}; fixed (int *b = a) { fixed (int *c = b) { }  // CS0213 // try the following line instead // int *c = b; } } }  
```