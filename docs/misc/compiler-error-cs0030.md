---
title: "컴파일러 오류 CS0030 | Microsoft Docs"
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
  - "CS0030"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0030"
ms.assetid: 3c9bd3f9-dea2-46dd-be1e-46c843ffd3de
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0030
'type' 형식을 'type'으로 변환할 수 없습니다.  
  
 특정 연산자 오버로드를 지원하려면 변환 루틴을 제공해야 합니다. 자세한 내용은 [변환 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/conversion-operators)을 참조하세요.  
  
 다음 샘플에서는 CS0030을 생성합니다.  
  
```  
// CS0030.cs namespace x { public class iii { /* public static implicit operator iii(int aa) { return null; } public static implicit operator int(iii aa) { return 0; } */ public static iii operator ++(iii aa) { return (iii)0;   // CS0030 // uncomment the conversion routines to resolve CS0030 } public static void Main() { } } }  
```