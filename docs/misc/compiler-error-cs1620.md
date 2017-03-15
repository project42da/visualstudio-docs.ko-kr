---
title: "컴파일러 오류 CS1620 | Microsoft Docs"
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
  - "CS1620"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1620"
ms.assetid: 13933976-218a-4fe2-8fde-5b9af522e2e5
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1620
'number' 인수는 'keyword' 키워드와 함께 전달해야 합니다.  
  
 이 오류는 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수를 사용하는 함수에 인수를 전달하며 호출 지점에 `ref` 또는 `out` 키워드를 포함하지 않거나 잘못된 키워드를 포함하는 경우에 발생합니다. 오류 텍스트는 사용할 적절한 키워드와 오류를 발생시킨 인수를 나타냅니다.  
  
 다음 샘플에서는 CS1620을 생성합니다.  
  
```  
// CS1620.cs class C { void f(ref int i) {} public static void Main() { int x = 1; f(out x);  // CS1620 – f takes a ref parameter, not an out parameter // Try this line instead: // f(ref x); } }  
```