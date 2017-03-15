---
title: "컴파일러 오류 CS1007 | Microsoft Docs"
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
  - "CS1007"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1007"
ms.assetid: b56ee2c6-8e79-4b9b-8c59-194bdb22bc3e
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1007
속성 접근자가 이미 정의되었습니다.  
  
 [속성](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)을 선언하는 경우 해당 접근자 메서드도 선언해야 합니다. 그러나 속성에 하나 이상의 `get` 접근자 메서드 또는 하나 이상의 `set` 접근자 메서드가 있을 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS1007을 생성합니다.  
  
```  
// CS1007.cs public class clx { public int MyProperty { get { return 0; } get   // CS1007, this is the second get method { return 0; } } public static void Main() {} }  
```