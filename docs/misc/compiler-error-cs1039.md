---
title: "컴파일러 오류 CS1039 | Microsoft Docs"
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
  - "CS1039"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1039"
ms.assetid: 266e9f7f-fe17-445a-aefd-6b7795167d68
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1039
문자열 리터럴이 종료되지 않았습니다.  
  
 컴파일러에서 잘못된 형식의 [문자열](/dotnet/csharp/language-reference/keywords/string) 리터럴을 검색했습니다.  
  
## 예제  
 다음 샘플에서는 CS1039를 생성합니다. 이 오류를 해결하려면 종료 따옴표를 추가합니다.  
  
```  
// CS1039.cs public class MyClass { public static void Main() { string b = @"hello, world;   // CS1039 } }  
```