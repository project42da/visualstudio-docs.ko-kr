---
title: "컴파일러 오류 CS0242 | Microsoft Docs"
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
  - "CS0242"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0242"
ms.assetid: bc86a5a4-89c1-4de4-a874-4dd4cbf592c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0242
요청한 작업이 void 포인터에 정의되어 있지 않습니다.  
  
 Void 포인터 증분이 허용되지 않습니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)을 참조하세요.  
  
 다음 샘플에서는 CS0242를 생성합니다.  
  
```  
// CS0242.cs // compile with: /unsafe class TestClass { public unsafe void Test() { void * p = null; p++;   // CS0242, incrementing a void pointer not allowed } public static void Main() { } }  
```