---
title: "컴파일러 오류 CS1024 | Microsoft Docs"
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
  - "CS1024"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1024"
ms.assetid: 41f587cb-1958-4eb6-9f8d-c03500e55e21
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1024
전처리기 지시문이 필요합니다.  
  
 줄이 파운드 기호\(\#\)로 시작하지만 후속 문자열이 유효한 [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)이 아니었습니다.  
  
 다음 샘플에서는 CS1024를 생성합니다.  
  
```  
// CS1024.cs #import System   // CS1024  
```