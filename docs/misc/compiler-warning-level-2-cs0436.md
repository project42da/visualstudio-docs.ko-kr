---
title: "컴파일러 경고(수준 2) CS0436 | Microsoft Docs"
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
  - "CS0436"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0436"
ms.assetid: c4135d9d-3511-4bbc-9540-48c2091f869c
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0436
'assembly'의 'type' 형식이 'assembly'에서 가져온 형식 'type2'와 충돌합니다. 'assembly'에 정의된 형식을 사용합니다.  
  
 이 경고는 원본 파일\(file\_2\)의 형식이 file\_1의 가져온 형식과 충돌할 때 발생합니다. 컴파일러에서는 원본 파일에 있는 네임스페이스를 사용합니다.  
  
## 예제  
  
```  
// CS0436_a.cs // compile with: /target:library public class A { public void Test() { System.Console.WriteLine("CS0436_a"); } }  
```  
  
## 예제  
 다음 예제에서는 CS0436을 생성합니다.  
  
```  
// CS0436_b.cs // compile with: /reference:CS0436_a.dll // CS0436 expected public class A { public void Test() { System.Console.WriteLine("CS0436_b"); } } public class Test { public static void Main() { A x = new A(); x.Test(); } }  
```