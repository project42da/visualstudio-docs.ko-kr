---
title: "컴파일러 경고(수준 2) CS0437 | Microsoft Docs"
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
  - "CS0437"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0437"
ms.assetid: cba5c9b6-a0bc-4f19-b1f0-c1f66436ee91
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0437
'assembly2'의 'type' 형식이 'fassembly1'의 가져온 네임스페이스 'namespace'와 충돌합니다. 'assembly'에 정의된 형식을 사용합니다.  
  
 이 경고는 소스 파일 file\_2의 형식이 file\_1의 가져온 네임스페이스와 충돌할 때 발생합니다. 컴파일러는 소스 파일에 있는 형식을 사용합니다.  
  
## 예제  
  
```  
// CS0437_a.cs // compile with: /target:library namespace Util { public class A { public void Test() { System.Console.WriteLine("CS0437_a.cs"); } } }  
```  
  
## 예제  
 다음 샘플에서는 CS0437을 생성합니다.  
  
```  
// CS0437_b.cs // compile with: /reference:CS0437_a.dll /W:2 // CS0437 expected class Util { public class A { public void Test() { System.Console.WriteLine("CS0437_b.cs"); } } } public class Test { public static void Main() { Util.A x = new Util.A(); x.Test(); } }  
```