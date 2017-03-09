---
title: "컴파일러 오류 CS1035 | Microsoft Docs"
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
  - "CS1035"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1035"
ms.assetid: 99125500-62de-421a-b12b-04311c8947c3
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1035
파일 끝\(EOF\)이 있습니다. '\*\/'가 필요합니다.  
  
 여는 주석 구분 기호와 닫는 구분 기호의 짝이 맞지 않습니다.  
  
 다음 샘플에서는 CS1035를 생성합니다.  
  
```  
// CS1035.cs public class a { public static void Main() { } } /*   // CS1035, needs closing comment  
```