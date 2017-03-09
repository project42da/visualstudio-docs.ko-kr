---
title: "컴파일러 경고(수준 4) CS0402 | Microsoft Docs"
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
  - "CS0402"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0402"
ms.assetid: 5a252c95-18c7-4569-bae0-e1f7b582cf6a
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS0402
'identifier': 진입점은 제네릭 또는 제네릭 형식일 수 없습니다.  
  
 진입점이 제네릭 형식으로 발견되었습니다. 이 경고를 제거하려면 제네릭이 아닌 클래스 또는 구조체로 Main을 구현합니다.  
  
```  
// CS0402.cs // compile with: /W:4 class C<T> { public static void Main()  // CS0402 { } } class CMain { public static void Main() {} }  
```