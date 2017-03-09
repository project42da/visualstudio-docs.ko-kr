---
title: "컴파일러 경고(수준 2) CS0435 | Microsoft Docs"
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
  - "CS0435"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0435"
ms.assetid: e70cd8c1-d399-4af8-8b1e-69a1de389aad
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0435
'assembly'의 'namespace' 네임스페이스가 'assembly'에서 가져온 형식 'type'과 충돌합니다. 'assembly'에 정의된 네임스페이스를 사용합니다.  
  
 이 경고는 원본 파일\(file\_2\)의 네임스페이스가 file\_1의 가져온 형식과 충돌할 때 발생합니다. 컴파일러에서는 원본 파일에 있는 네임스페이스를 사용합니다.  
  
 다음 예제에서는 CS0435를 생성합니다.  
  
 먼저 아래 파일을 컴파일합니다.  
  
```  
// CS0435_1.cs // compile with: /t:library public class Util { public class A { } }  
```  
  
 그런 다음 아래 파일을 컴파일합니다.  
  
```  
// CS0435_2.cs // compile with: /r:CS0435_1.dll using System; namespace Util { public class A { } } public class Test { public static void Main() { Console.WriteLine(typeof(Util.A)); // CS0435 } }  
```