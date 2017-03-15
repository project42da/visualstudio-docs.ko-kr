---
title: "컴파일러 경고(수준 4) CS0078 | Microsoft Docs"
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
  - "CS0078"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0078"
ms.assetid: 8d637be6-82bc-462c-bec5-217327bc8c40
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS0078
접미사 'l'은 숫자 '1'과 쉽게 혼동됩니다. 쉽게 구별할 수 있도록 'L'을 사용하세요.  
  
 대문자 L이 아닌 소문자 l이 오래 사용 중인 경우 컴파일러에서 경고를 표시합니다.  
  
 다음 샘플에서는 CS0078을 생성합니다.  
  
```  
// CS0078.cs // compile with: /W:4 class test { public static void TestL(long i) { } public static void TestL(int i) { } public static void Main() { TestL(25l);   // CS0078 // try the following line instead // TestL(25L); } }  
```