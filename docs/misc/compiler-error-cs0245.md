---
title: "컴파일러 오류 CS0245 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0245"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0245"
ms.assetid: 3f2beb2f-a510-4568-9d11-bb1f65066acd
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0245
소멸자 및 object.Finalize는 직접 호출할 수 없습니다. 가능한 경우 IDisposable.Dispose를 호출하세요.  
  
 자세한 내용은 [가비지 수집에 대한 프로그래밍 정보](../Topic/Garbage%20Collection.md) 및 [소멸자](/dotnet/csharp/programming-guide/classes-and-structs/destructors)를 참조하세요.  
  
 다음 샘플에서는 CS0245를 생성합니다.  
  
```  
// CS0245.cs using System; using System.Collections; class MyClass // : IDisposable { /* public void Dispose() { // cleanup code goes here } */ void m() { this.Finalize();   // CS0245 // this.Dispose(); } public static void Main() { } }  
```