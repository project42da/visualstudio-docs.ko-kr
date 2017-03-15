---
title: "컴파일러 오류 CS1681 | Microsoft Docs"
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
  - "CS1681"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1681"
ms.assetid: 99934e15-1db8-4b71-9da8-a681a1d47407
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1681
전역 extern 별칭을 다시 정의할 수 없습니다.  
  
 별칭이 지정되지 않은 모든 참조를 포함하도록 전역 별칭이 이미 정의되었으므로 다시 정의할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS1681을 생성합니다.  
  
```  
// CS1681.cs // compile with: /reference:global=System.dll // CS1681 expected // try this instead: /reference:System.dll class A { static void Main() {} }  
```