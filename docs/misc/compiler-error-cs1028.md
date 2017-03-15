---
title: "컴파일러 오류 CS1028 | Microsoft Docs"
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
  - "CS1028"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1028"
ms.assetid: 9df07db3-256f-45e9-8323-26539c55a1d8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1028
예기치 않은 전처리기 지시문이 있습니다.  
  
 [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)이 있는데 필요하지 않습니다.  
  
 예를 들어 앞에 `#if`가 없는 `#endif`가 있습니다.  
  
 다음 샘플에서는 CS1028을 생성합니다.  
  
```  
// CS1028.cs #endif   // CS1028, no matching #if namespace x { public class clx { public static void Main() { } } }  
```