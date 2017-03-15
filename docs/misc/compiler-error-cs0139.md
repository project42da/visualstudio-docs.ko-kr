---
title: "컴파일러 오류 CS0139 | Microsoft Docs"
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
  - "CS0139"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0139"
ms.assetid: 235ba3d4-566c-4ef6-801a-a338f4f2a12d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0139
break 또는 continue되어 빠져 나갈 루프가 없습니다.  
  
 break 또는 continue 문이 루프 외부에서 발생했습니다.  
  
 자세한 내용은 [점프 문](/dotnet/csharp/language-reference/keywords/jump-statements)을 참조하세요.  
  
 다음 샘플에서는 CS0139를 두 번 생성합니다.  
  
```  
// CS0139.cs namespace x { public class a { public static void Main() { continue;  // CS0139 break;     // CS0139 } } }  
```