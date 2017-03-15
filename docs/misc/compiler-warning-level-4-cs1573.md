---
title: "컴파일러 경고(수준 4) CS1573 | Microsoft Docs"
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
  - "CS1573"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1573"
ms.assetid: 1b68cb1a-9bfd-4343-b9b6-8ce195af5e23
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS1573
'parameter' 매개 변수와 짝이 맞는 매개 변수 태그가 'parameter'의 XML 주석에 없습니다. 다른 매개 변수는 짝이 맞는 태그가 있습니다.  
  
 [\/doc](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option) 컴파일러 옵션을 사용할 때 주석이 메서드의 모든 매개 변수가 아닌 일부에 대해 지정되었습니다. 이러한 매개 변수에 대해 주석을 입력하는 것을 잊었을 수도 있습니다.  
  
 다음 샘플에서는 CS1573을 생성합니다.  
  
```  
// CS1573.cs // compile with: /W:4 public class MyClass { /// <param name='Int1'>Used to indicate status.</param> // enter a comment for Char1? public static void MyMethod(int Int1, char Char1) { } public static void Main () { } }  
```