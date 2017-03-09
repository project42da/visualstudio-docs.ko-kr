---
title: "컴파일러 오류 CS1025 | Microsoft Docs"
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
  - "CS1025"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1025"
ms.assetid: 491c186f-cb40-47a9-9656-44fadfa18ae2
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1025
한 줄로 된 주석이나 줄 끝\(EOL\)이 필요합니다.  
  
 [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)이 포함된 줄에 여러 줄 주석을 사용할 수 없습니다.  
  
 다음 샘플에서는 CS1025를 생성합니다.  
  
```  
#if true /* hello */   // CS1025 #endif   // this is a good comment  
```  
  
 다음과 같이 잘못된 전처리기 지시문을 시도하는 경우에도 CS1025가 발생할 수 있습니다.  
  
```  
// CS1025.cs #define a class Sample { static void Main() { #if a 1   // CS1025, invalid syntax System.Console.WriteLine("Hello, World!"); #endif } }  
```