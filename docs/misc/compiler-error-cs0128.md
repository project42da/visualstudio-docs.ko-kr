---
title: "컴파일러 오류 CS0128 | Microsoft Docs"
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
  - "CS0128"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0128"
ms.assetid: 35db9025-2bed-437f-a78a-f2862766bde2
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0128
'variable'이라는 지역 변수가 이미 이 범위 안에 정의되어 있습니다.  
  
 컴파일러가 동일한 이름을 가진 두 개의 지역 변수 선언을 발견했습니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
 다음 샘플에서는 CS0128을 생성합니다.  
  
```  
// CS0128.cs namespace MyNamespace { public class MyClass { public static void Main() { char i; int i;   // CS0128 } } }  
```