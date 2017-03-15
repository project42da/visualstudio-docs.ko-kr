---
title: "컴파일러 오류 CS0170 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0170"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0170"
ms.assetid: ba881e38-2abf-4a5f-b9e6-28d26a5bd235
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0170
할당되지 않은 'field' 필드를 사용하고 있는 것 같습니다.  
  
 구조체의 필드를 먼저 초기화하지 않고 사용했습니다. 이 문제를 해결하려면 먼저 초기화되지 않은 필드를 확인하고 이를 초기화한 다음 액세스를 시도합니다. 구조체를 초기화하는 방법에 대한 자세한 내용은 [구조체](/dotnet/csharp/programming-guide/classes-and-structs/structs) 및 [구조체 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-structs)을 참조하세요.  
  
 다음 샘플에서는 CS0170을 생성합니다.  
  
```  
// CS0170.cs public struct error { public int i; } public class MyClass { public static void Main() { error e; // uncomment the next line to resolve this error // e.i = 0; System.Console.WriteLine( e.i );   // CS0170 because //e.i was never assigned } }  
```