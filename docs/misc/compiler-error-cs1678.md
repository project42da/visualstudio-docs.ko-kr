---
title: "컴파일러 오류 CS1678 | Microsoft Docs"
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
  - "CS1678"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1678"
ms.assetid: 2be8aa17-81e2-47b0-b239-e41e0c5c0d97
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1678
'number' 매개 변수가 'type1' 형식으로 선언되었는데 'type2'로 선언되어야 합니다.  
  
 이 오류는 무명 메서드의 매개 변수 형식이 메서드를 캐스팅하는 대리자의 선언과 다른 경우 발생합니다.  
  
 다음 샘플에서는 CS1678을 생성합니다.  
  
```  
// CS1678 delegate void D(int i); class Errors { static void Main() { D d = delegate(string s) { };   // CS1678 // To resolve, use the following line instead: // D d = delegate(int s) { }; } }  
```