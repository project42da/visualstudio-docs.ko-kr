---
title: "컴파일러 오류 CS1008 | Microsoft Docs"
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
  - "CS1008"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1008"
ms.assetid: e595a431-2cf0-4cc1-998f-94aecb2a6db1
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1008
byte, sbyte, short, ushort, int, uint, long 또는 ulong 형식이 필요합니다.  
  
 [열거형](/dotnet/csharp/language-reference/keywords/enum)과 같은 특정 데이터 형식을 선언해야만 지정된 형식의 데이터를 유지할 수 있습니다.  
  
 다음 샘플에서는 CS1008을 생성합니다.  
  
```  
// CS1008.cs abstract public class clx { enum splitch : char   // CS1008, char not valid type for enums { x, y, z } public static void Main() { } }  
```