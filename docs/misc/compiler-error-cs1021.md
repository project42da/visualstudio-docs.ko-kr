---
title: "컴파일러 오류 CS1021 | Microsoft Docs"
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
  - "CS1021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1021"
ms.assetid: 0346ba58-d7cd-40bd-bcad-b90117fdc9b5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1021
정수 계열 상수가 너무 큽니다.  
  
 [정수 형식](/dotnet/csharp/language-reference/keywords/integral-types-table)에 할당된 값이 부호 없는 가능한 최대 정수 값보다 더 큽니다.  
  
 다음 샘플에서는 CS1021을 생성합니다.  
  
```  
// CS1021.cs enum F : int { a=(int)2590000000000000000000   // CS1021 } public class clx { public static void Main() { } }  
```