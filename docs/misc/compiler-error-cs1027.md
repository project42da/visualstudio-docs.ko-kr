---
title: "컴파일러 오류 CS1027 | Microsoft Docs"
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
  - "CS1027"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1027"
ms.assetid: a6657f0f-5664-47a5-95cf-803f5a0e0c90
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1027
\#endif 지시문이 필요합니다.  
  
 지정된 `#if` 지시문에 일치하는 `#endif` [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)이 없습니다. 또는 해당하는 `#region` 지시문이 `#if` 블록에 없는데 컴파일러에서 `#endregion` 지시문을 찾았을 수 있습니다.  
  
 다음 샘플에서는 CS1027을 생성합니다.  
  
```  
// CS1027.cs #if true   // CS1027, uncomment next line to resolve // #endif namespace x { public class clx { public static void Main() { } } }  
```