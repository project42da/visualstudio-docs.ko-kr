---
title: "컴파일러 오류 CS0543 | Microsoft Docs"
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
  - "CS0543"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0543"
ms.assetid: f85e09a7-0e08-4dea-8f64-218c0876e4f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0543
'enumeration': 열거자 값이 너무 커서 해당 형식에 맞지 않습니다.  
  
 [열거형](/dotnet/csharp/language-reference/keywords/enum)의 요소에 할당된 값이 데이터 형식의 범위를 벗어났습니다.  
  
 다음 샘플에서는 CS0543을 생성합니다.  
  
```  
// CS0543.cs namespace x { enum I : byte {a = 255, b, c}   // CS0543 public class clx { public static int Main() { return 0; } } }  
```