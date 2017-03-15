---
title: "컴파일러 오류 CS0500 | Microsoft Docs"
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
  - "CS0500"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0500"
ms.assetid: b1a45708-702b-482c-bd71-c0c2531e29f3
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0500
'class member'는 abstract로 표시되어 있으므로 본문을 선언할 수 없습니다.  
  
 [abstract](/dotnet/csharp/language-reference/keywords/abstract) 메서드는 구현을 포함할 수 없습니다.  
  
 다음 샘플에서는 CS0500을 생성합니다.  
  
```  
// CS0500.cs namespace x { abstract public class clx { abstract public void f(){}   // CS0500 // try the following line instead // abstract public void f(); } public class cly { public static int Main() { return 0; } } }  
```