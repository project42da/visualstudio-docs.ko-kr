---
title: "컴파일러 오류 CS0185 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0185"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0185"
ms.assetid: d6546e10-0af3-4860-8e6f-2da7dbeb3d28
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0185
'type'은 lock 문에 필요한 참조 형식이 아닙니다.  
  
 [lock](/dotnet/csharp/language-reference/keywords/lock-statement) 문은 참조 형식을 평가만 할 수 있습니다. 자세한 내용은 [스레드 동기화](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md) 및 [참조 형식](/dotnet/csharp/language-reference/keywords/reference-types)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0185를 생성합니다.  
  
```  
// CS0185.cs public class MainClass { public static void Main () { lock (1)   // CS0185 // try the following lines instead // MainClass x = new MainClass(); // lock(x) { } } }  
```