---
title: "컴파일러 경고(수준 4) CS0628 | Microsoft Docs"
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
  - "CS0628"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0628"
ms.assetid: a54cfad8-27c9-4abb-8c83-982615489a10
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS0628
'member': sealed 클래스에 새 protected 멤버가 선언되었습니다.  
  
 [sealed](/dotnet/csharp/language-reference/keywords/sealed) 클래스에는 [protected](/dotnet/csharp/language-reference/keywords/protected) 멤버를 사용할 수 없습니다. 다른 클래스는 `sealed` 클래스에서 상속하거나 `protected` 멤버를 사용할 수 없기 때문입니다.  
  
 다음 샘플에서는 CS0628을 생성합니다.  
  
```  
// CS0628.cs // compile with: /W:4 sealed class C { protected int i;   // CS0628 } class MyClass { public static void Main() { } }  
```