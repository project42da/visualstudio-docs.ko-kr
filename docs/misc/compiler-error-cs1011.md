---
title: "컴파일러 오류 CS1011 | Microsoft Docs"
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
  - "CS1011"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1011"
ms.assetid: d4568471-b0f8-4c24-89f3-9c543521d1d8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1011
빈 문자 리터럴입니다.  
  
 [char](/dotnet/csharp/language-reference/keywords/char)가 선언되고 null로 초기화되었습니다.`char` 초기화에서는 한 문자를 지정해야 합니다.  
  
 다음 샘플에서는 CS1011을 생성합니다.  
  
```  
// CS1011.cs class Sample { public char CharField = '';   // CS1011 }  
```