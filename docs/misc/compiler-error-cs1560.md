---
title: "컴파일러 오류 CS1560 | Microsoft Docs"
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
  - "CS1560"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1560"
ms.assetid: 772c4543-6c8d-453f-ae3f-d333528eb8b3
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1560
전처리기 지시문에 지정한 파일 이름이 잘못되었습니다. 파일 이름이 너무 길거나 유효한 파일 이름이 아닙니다.  
  
 [\#line](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-line)을 사용하여 지정된 파일 이름이 \_MAX\_PATH\(256자\)를 초과했거나 `#line`이 있는 줄이 2000자를 초과했습니다.  
  
## 예제  
 다음 샘플에서는 CS1560을 생성합니다.  
  
```  
// cs1560.cs using System; class MyClass { public static void Main() { Console.WriteLine("Normal line #1."); #line 21 "MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890.txt"   // CS1560 } }  
```