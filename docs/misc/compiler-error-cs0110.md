---
title: "컴파일러 오류 CS0110 | Microsoft Docs"
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
  - "CS0110"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0110"
ms.assetid: 0bfe7071-1194-4142-a1a1-6190ee92b1d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0110
'const declaration'에 대한 상수 값 계산에 순환 정의가 포함되어 있습니다.  
  
 [const](/dotnet/csharp/language-reference/keywords/const) 변수\(`a`\) 선언에서 역시 \(`a`\)를 참조하는 다른 const 변수\(`b`\)를 참조할 수 없습니다.  
  
 다음 샘플에서는 CS0110을 생성합니다.  
  
```  
// CS0110.cs namespace MyNamespace { public class A { public static void Main() { } } public class B : A { public const int i = c + 1;   // CS0110, c already references i public const int c = i + 1; // the following line would be OK // public const int c = 10; } }  
```  
  
## 참고 항목  
 [상수](/dotnet/csharp/programming-guide/classes-and-structs/constants)