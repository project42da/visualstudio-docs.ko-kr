---
title: "컴파일러 오류 CS1023 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1023"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1023"
ms.assetid: 27d70f2c-9ae1-459c-a6be-01ed5a3eea07
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1023
포함 문은 선언 또는 레이블 문일 수 없습니다.  
  
 **if** 문 다음에 오는 문과 같이 포함된 문에는 선언 또는 레이블 문을 포함할 수 없습니다.  
  
 다음 샘플에서는 CS1023을 두 번 생성합니다.  
  
```  
// CS1023.cs public class a { public static void Main() { if (1) int i;      // CS1023, declaration is not valid here if (1) xx : i++;   // CS1023, labeled statement is not valid here } }  
```