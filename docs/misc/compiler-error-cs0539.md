---
title: "컴파일러 오류 CS0539 | Microsoft Docs"
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
  - "CS0539"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0539"
ms.assetid: 41b8975c-abd1-4a36-98a4-8efa5fb0502a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0539
명시적 인터페이스 선언에서 'member'는 인터페이스의 멤버가 아닙니다.  
  
 존재하지 않는 [인터페이스](/dotnet/csharp/language-reference/keywords/interface) 멤버를 명시적으로 선언하려고 했습니다. 선언을 삭제하거나 유효한 인터페이스 멤버를 참조하도록 변경해야 합니다.  
  
 다음 샘플에서는 CS0539를 생성합니다.  
  
```  
// CS0539.cs namespace x { interface I { void m(); } public class clx : I { void I.x()   // CS0539 { } public static int Main() { return 0; } } }  
```