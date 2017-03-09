---
title: "컴파일러 오류 CS1536 | Microsoft Docs"
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
  - "CS1536"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1536"
ms.assetid: 65f14fbb-df79-4759-8911-93f8f90f5a60
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1536
void 매개 변수 형식이 잘못되었습니다.  
  
 void 포인터 이외의 [void](/dotnet/csharp/language-reference/keywords/void) 매개 변수를 지정하는 것은 불필요하거나 유효하지 않습니다.  
  
 다음 샘플에서는 CS1536을 생성합니다.  
  
```  
// CS1536.cs class a { public static int x( void )   // CS1536 // try the following line instead // public static int x() { return 0; } public static void Main() { } }  
```