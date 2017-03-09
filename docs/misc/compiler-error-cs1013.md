---
title: "컴파일러 오류 CS1013 | Microsoft Docs"
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
  - "CS1013"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1013"
ms.assetid: e5b1d24d-e558-4f7c-b2b1-3a644710005d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1013
숫자가 잘못되었습니다.  
  
 컴파일러가 잘못된 형식의 숫자를 검색했습니다. 정수 형식에 대한 자세한 내용은 [정수 계열 형식 표](/dotnet/csharp/language-reference/keywords/integral-types-table)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1013을 생성합니다.  
  
```  
// CS1013.cs class Sample { static void Main() { int i = 0x;   // CS1013 } }  
```