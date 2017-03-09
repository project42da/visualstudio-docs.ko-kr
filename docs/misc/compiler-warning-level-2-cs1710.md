---
title: "컴파일러 경고(수준 2) CS1710 | Microsoft Docs"
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
  - "CS1710"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1710"
ms.assetid: 03c66a8d-30fc-4387-87f6-de759ec7ee88
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1710
'type'의 XML 주석에 'parameter'에 대한 중복된 형식 매개 변수 태그가 있습니다.  
  
 제네릭 형식의 설명서에 형식 매개 변수에 대한 중복된 태그가 포함되어 있습니다.  
  
## 예제  
 다음 코드는 CS1710 경고가 표시되게 합니다.  
  
```  
// CS1710.cs // compile with: /doc:cs1710.xml // To resolve this warning, delete one of the duplicate <typeparam>'s. using System; class Stack<ItemType> { } /// <typeparam name="MyType">can be an int</typeparam> /// <typeparam name="MyType">can be an int</typeparam> class MyStackWrapper<MyType> { // Open constructed type Stack<MyType>. Stack<MyType> stack; public MyStackWrapper(Stack<MyType> s) { stack = s; } } class CMain { public static void Main() { // Closed constructed type Stack<int>. Stack<int> stackInt = new Stack<int>(); MyStackWrapper<int> MyStackWrapperInt = new MyStackWrapper<int>(stackInt); } }  
```