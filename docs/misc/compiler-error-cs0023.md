---
title: "컴파일러 오류 CS0023 | Microsoft Docs"
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
  - "CS0023"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0023"
ms.assetid: 7a30073c-99de-41fa-ac6d-4a0dfbb76de9
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0023
'operator' 연산자는 'type' 형식의 피연산자에 적용할 수 없습니다.  
  
 형식이 연산자에서 작동하도록 설계되지 않은 변수에 연산자를 적용하려고 했습니다. 자세한 내용은 [형식](/dotnet/csharp/programming-guide/types/index) 및 [C\# 연산자](/dotnet/csharp/language-reference/operators/index)를 참조하세요.  
  
 다음 샘플에서는 CS0023을 생성합니다.  
  
```  
// CS0023.cs namespace x { public class a { public static void Main() { string s = "hello"; s = -s;   // CS0023, minus operator not allowed on strings } } }  
```