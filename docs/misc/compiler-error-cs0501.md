---
title: "컴파일러 오류 CS0501 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0501"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0501"
ms.assetid: 3ff45208-5b9b-42f6-8a12-1eb38a665f33
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0501
'member function'은 abstract, extern 또는 partial로 표시되어 있지 않으므로 본문을 선언해야 합니다.  
  
 비추상 메서드에는 구현이 있어야 합니다.  
  
 다음 샘플에서는 CS0501을 생성합니다.  
  
```  
// CS0501.cs // compile with: /target:library public class clx { public void f();   // CS0501 declared but not defined public void g() {}   // OK }  
```