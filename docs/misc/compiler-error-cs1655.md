---
title: "컴파일러 오류 CS1655 | Microsoft Docs"
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
  - "CS1655"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1655"
ms.assetid: 041e9daa-c026-494f-b086-0db9a23c969b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1655
'variable'은 'readonly variable type'이므로 해당 필드를 ref 또는 out 인수로 전달할 수 없습니다.  
  
 이 오류는 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 변수, [using](/dotnet/csharp/language-reference/keywords/using-statement) 변수 또는 [fixed](/dotnet/csharp/language-reference/keywords/fixed-statement) 변수의 멤버를 ref 또는 out 인수로 함수에 전달하려는 경우에 발생합니다. 해당 변수는 이러한 컨텍스트에서 읽기 전용으로 간주되므로 이 작업을 수행할 수 없습니다.  
  
 다음 샘플에서는 CS1655를 생성합니다.  
  
```  
// CS1655.cs struct S { public int i; } class CMain { static void f(ref int iref) { } public static void Main() { S[] sa = new S[10]; foreach(S s in sa) { CMain.f(ref s.i);  // CS1655 } } }  
```