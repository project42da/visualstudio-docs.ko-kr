---
title: "컴파일러 경고(수준 1) CS0184 | Microsoft Docs"
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
  - "CS0184"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0184"
ms.assetid: 55e73f76-f502-4d15-88fc-bd5757b512a4
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0184
지정된 식은 제공된 \('type'\) 형식이 아닙니다.  
  
 테스트 중인 변수가 ***type***으로 선언되거나 ***type***에서 파생되지 않았으므로 식은 **true**가 될 수 없습니다.  
  
 다음 샘플에서는 CS0184를 생성합니다.  
  
```  
// CS0184.cs // compile with: /W:1 class MyClass { public static void Main() { int i = 0; if (i is string)   // CS0184 i++; } }  
```