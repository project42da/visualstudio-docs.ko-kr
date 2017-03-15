---
title: "컴파일러 오류 CS1663 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1663"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1663"
ms.assetid: 013f36ac-8925-4cee-9008-54fa7ad1324b
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1663
고정 크기 버퍼는 bool, byte, short, int, long, char, sbyte, ushort, uint, ulong, float 또는 double 형식 중 하나여야 합니다.  
  
 고정 크기 버퍼는 목록에 있는 형식 이외의 형식일 수 없습니다. 이 오류를 방지하려면 다른 형식을 사용하거나 고정된 배열을 사용하지 마세요.  
  
## 예제  
 다음 샘플에서는 CS1663을 생성합니다.  
  
```  
// CS1663.cs // compile with: /unsafe /target:library unsafe struct C { fixed string ab[10];   // CS1663 }  
```