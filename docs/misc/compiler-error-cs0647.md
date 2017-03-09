---
title: "컴파일러 오류 CS0647 | Microsoft Docs"
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
  - "CS0647"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0647"
ms.assetid: b62d7fc9-4711-428e-ab66-09ea1c9970f0
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0647
'attribute' 특성을 내보내는 동안 오류가 발생했습니다. 'reason'  
  
 다음 샘플에서는 CS0647을 생성합니다.  
  
```  
// CS0647.cs using System.Runtime.InteropServices; [Guid("z")]   // CS0647, incorrect uuid format. // try the following line instead // [Guid("00000000-0000-0000-0000-000000000001")] public class MyClass { public static void Main() { } }  
```