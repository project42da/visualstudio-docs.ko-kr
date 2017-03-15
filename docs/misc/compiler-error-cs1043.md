---
title: "컴파일러 오류 CS1043 | Microsoft Docs"
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
  - "CS1043"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1043"
ms.assetid: 749703a1-d8ac-4be6-9c48-753f64ae92a1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1043
{ 또는 ;이 필요합니다.  
  
 속성 접근자가 잘못 선언되었습니다. 자세한 내용은 [속성 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1043을 생성합니다.  
  
```  
// CS1043.cs // compile with: /target:library public class MyClass { public int DoSomething { get return 1;   // CS1043 set {} } // OK public int DoSomething2 { get { return 1;} } }  
```