---
title: "컴파일러 오류 CS1959 | Microsoft Docs"
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
  - "CS1959"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1959"
ms.assetid: 20a31619-3e30-446a-becc-a7f8cfcec66d
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1959
'name'은 'type' 형식입니다. 상수 선언에 지정되는 형식은 sbyte, byte, short, ushort, int, uint, long, ulong, char, float, double, decimal, bool, string, enum\-type 또는 reference\-type이어야 합니다.  
  
 상수 선언에 허용되는 형식은 이 메시지에서 설명하는 형식으로 제한됩니다.  
  
### 이 오류를 해결하려면  
  
1.  허용되는 형식을 사용하여 상수를 선언합니다.  
  
## 예제  
 다음 코드에서는 `null`은 형식이 아니므로 CS1959를 생성합니다.  
  
```  
// cs1959.cs class Program { static void Test<T>() where T : class { const T x = null; // CS1959 } }  
```  
  
## 참고 항목  
 [상수](/dotnet/csharp/programming-guide/classes-and-structs/constants)   
 [null](/dotnet/csharp/language-reference/keywords/null)