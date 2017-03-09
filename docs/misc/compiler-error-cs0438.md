---
title: "컴파일러 오류 CS0438 | Microsoft Docs"
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
  - "CS0438"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0438"
ms.assetid: 92c91ecb-8d6a-4850-84eb-c095c3c957f1
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0438
'module\_1'의 'type' 형식이 'module\_2'의 ‘namespace' 네임스페이스와 충돌합니다.  
  
 소스 파일의 형식이 다른 소스 파일의 네임스페이스와 충돌하는 경우 이 오류가 발생합니다. 이 오류는 일반적으로 하나 또는 둘 다를 추가된 모듈에서 가져올 때 발생합니다. 해결하려면 충돌을 일으킨 형식 또는 네임스페이스의 이름을 바꿉니다.  
  
 다음 예제에서는 CS0438을 생성합니다.  
  
 먼저 아래 파일을 컴파일합니다.  
  
```  
// CS0438_1.cs // compile with: /target:module public class Util { public class A { } }  
```  
  
 그런 다음 아래 파일을 컴파일합니다.  
  
```  
// CS0438_2.cs // compile with: /target:module namespace Util { public class A { } }  
```  
  
 그런 다음 아래 파일을 컴파일합니다.  
  
```  
// CS0438_3.cs // compile with: /addmodule:CS0438_1.netmodule /addmodule:CS0438_2.netmodule using System; public class Test { public static void Main() { Console.WriteLine(typeof(Util.A));   // CS0438 } }  
  
```