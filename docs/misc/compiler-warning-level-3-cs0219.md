---
title: "컴파일러 경고(수준 3) CS0219 | Microsoft Docs"
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
  - "CS0219"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0219"
ms.assetid: 7945c497-4bfa-4695-9166-815a2ad0c8e7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0219
'variable' 변수가 할당되었지만 변수 값이 사용되지 않았습니다.  
  
 변수를 선언하고 할당하지만 사용하지 않을 경우 컴파일러에서 수준 3 경고를 실행합니다.  
  
 다음 샘플에서는 CS0219를 생성합니다.  
  
```  
// CS0219.cs // compile with: /W:3 public class MyClass { public static void Main() { int a = 0;   // CS0219 } }  
```