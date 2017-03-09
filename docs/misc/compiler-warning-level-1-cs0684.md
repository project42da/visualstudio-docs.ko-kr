---
title: "컴파일러 경고(수준 1) CS0684 | Microsoft Docs"
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
  - "CS0684"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0684"
ms.assetid: d6c8aaf6-c1cf-4c0e-b367-4c3e418d8bc4
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0684
'interface' 인터페이스는 'CoClassAttribute'로 표시되어 있고 'ComImportAttribute'로 표시되어 있지 않습니다.  
  
 인터페이스에서 **CoClassAttribute**를 지정한 경우 **ComImportAttribute**도 지정해야 합니다.  
  
 다음 샘플에서는 CS0684를 생성합니다.  
  
```  
// CS0684.cs // compile with: /W:1 using System; using System.Runtime.InteropServices; [CoClass(typeof(C))] // CS0684 // try the following line instead // [CoClass(typeof(C)), ComImport] interface I { } class C { static void Main() {} }  
```