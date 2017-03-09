---
title: "컴파일러 오류 CS1547 | Microsoft Docs"
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
  - "CS1547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1547"
ms.assetid: 40029557-076a-47d8-aabc-d86c56a846d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1547
이 컨텍스트에는 'void' 키워드를 사용할 수 없습니다.  
  
 컴파일러에서 [void](/dotnet/csharp/language-reference/keywords/void) 키워드가 잘못 사용된 것을 발견했습니다.  
  
 다음 샘플에서는 CS1547을 생성합니다.  
  
```  
// CS1547.cs public class MyClass { void BadMethod() { void i;   // CS1547, cannot have variables of type void } public static void Main() { } }  
```