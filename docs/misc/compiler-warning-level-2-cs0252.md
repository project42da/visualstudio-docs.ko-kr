---
title: "컴파일러 경고(수준 2) CS0252 | Microsoft Docs"
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
  - "CS0252"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0252"
ms.assetid: ff82fbac-01cf-4ae9-b6a0-3aa990096b46
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0252
의도하지 않은 참조 비교가 있을 수 있습니다. 값 비교를 가져오려면 왼쪽을 'type' 형식으로 캐스팅하세요.  
  
 컴파일러가 참조 비교를 수행합니다. 문자열의 값을 비교하려는 경우 식의 왼쪽을 `type`로 캐스트합니다.  
  
 다음 샘플에서는 CS0252를 생성합니다.  
  
```  
// CS0252.cs // compile with: /W:2 using System; class MyClass { public static void Main() { string s = "11"; object o = s + s; bool b = o == s;   // CS0252 // try the following line instead // bool b = (string)o == s; } }  
```