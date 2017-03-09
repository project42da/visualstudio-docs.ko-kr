---
title: "컴파일러 오류 CS0594 | Microsoft Docs"
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
  - "CS0594"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0594"
ms.assetid: a3d6bde1-db63-4c5c-a425-8c6a39e00999
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0594
부동 소수점 상수가 'type' 형식 범위 밖에 있습니다.  
  
 이 데이터 형식의 변수에 너무 큰 값이 부동 소수점 변수에 할당되었습니다. 데이터 형식에 허용되는 값 범위에 대한 자세한 내용은 [정수 형식 표](/dotnet/csharp/language-reference/keywords/integral-types-table)를 참조하세요.  
  
 다음 샘플에서는 CS0594를 생성합니다.  
  
```  
// CS0594.cs namespace MyNamespace { public class MyClass { public static void Main() { float f = 6.77777777777E400;   // CS0594, value too large } } }  
```