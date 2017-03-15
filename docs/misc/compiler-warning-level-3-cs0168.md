---
title: "컴파일러 경고(수준 3) CS0168 | Microsoft Docs"
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
  - "CS0168"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0168"
ms.assetid: 6f5b7fe3-1e91-462f-8a73-b931327ab3f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0168
'var' 변수가 할당되었지만 변수 값이 사용되지 않았습니다.  
  
 컴파일러는 변수가 선언되었지만 사용되지 않은 경우 경고를 표시합니다.  
  
 다음 샘플에서는 CS0168 경고를 생성합니다.  
  
```  
// CS0168.cs // compile with: /W:3 public class clx { public int i; } public class clz { public static void Main() { int j = 0;   // CS0168, uncomment the following line // j++; clx a;       // CS0168, try the following line instead // clx a = new clx(); } }  
```