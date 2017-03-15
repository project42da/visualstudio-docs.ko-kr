---
title: "컴파일러 오류 CS1040 | Microsoft Docs"
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
  - "CS1040"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1040"
ms.assetid: a988d665-ead5-489f-922d-ff2c4dd8a922
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1040
전처리기 지시문은 줄에서 공백이 아닌 첫 번째 문자로 나타나야 합니다.  
  
 줄에서 [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)을 찾았지만 줄의 첫 번째 토큰이 아닙니다. 지시문은 줄의 첫 번째 토큰이어야 합니다.  
  
 다음 샘플에서는 CS1040을 생성합니다.  
  
```  
// CS1040.cs /* Define a symbol, X */ #define X   // CS1040 // try the following two lines instead // /* Define a symbol, X */ // #define X public class MyClass { public static void Main() { } }  
```