---
title: "컴파일러 오류 CS0145 | Microsoft Docs"
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
  - "CS0145"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0145"
ms.assetid: e5f9a90f-1700-4e6a-8f82-23d0c0287b85
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0145
const 필드에 값을 입력해야 합니다.  
  
 [const](/dotnet/csharp/language-reference/keywords/const) 변수를 초기화해야 합니다. 자세한 내용은 [상수](/dotnet/csharp/programming-guide/classes-and-structs/constants)을 참조하세요.  
  
 다음 샘플에서는 CS0145를 생성합니다.  
  
```  
// CS0145.cs class MyClass { const int i;   // CS0145 // try the following line instead // const int i = 0; public static void Main() { } }  
```