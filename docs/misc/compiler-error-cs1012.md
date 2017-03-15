---
title: "컴파일러 오류 CS1012 | Microsoft Docs"
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
  - "CS1012"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1012"
ms.assetid: 4acc5fe0-da47-4882-b7d8-557767d7cf03
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1012
문자 리터럴에 문자가 너무 많습니다.  
  
 둘 이상의 문자를 사용하여 [char](/dotnet/csharp/language-reference/keywords/char) 상수를 초기화하려고 했습니다.  
  
 데이터 바인딩을 수행하는 경우에도 CS1012가 발생할 수 있습니다. 예를 들어 다음 줄에서는 오류가 발생합니다.  
  
 `<%# DataBinder.Eval(Container.DataItem, 'doctitle') %>`  
  
 대신 다음 줄을 사용해 보세요.  
  
 `<%# DataBinder.Eval(Container.DataItem, "doctitle") %>`  
  
 다음 샘플에서는 CS1012를 생성합니다.  
  
```  
// CS1012.cs class Sample { static void Main() { char a = 'xx';   // CS1012 char a2 = 'x';   // OK System.Console.WriteLine(a2); } }  
```