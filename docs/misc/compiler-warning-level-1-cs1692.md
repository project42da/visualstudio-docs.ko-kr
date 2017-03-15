---
title: "컴파일러 경고(수준 1) CS1692 | Microsoft Docs"
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
  - "CS1692"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1692"
ms.assetid: 1a6d52e1-0ebb-4990-ac0b-36b05a884a19
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1692
숫자가 잘못되었습니다.  
  
 `#pragma` 및 `#line` 등 많은 전처리기 지시문에서는 숫자를 매개 변수로 사용합니다. 이러한 숫자 중 하나가 올바르지 않습니다. 너무 길거나, 형식이 잘못되었거나, 잘못된 문자가 있습니다. 이 오류를 해결하려면 숫자를 수정합니다.  
  
## 예제  
 다음 예제는 CS1692를 생성합니다.  
  
```  
// CS1692.cs #pragma warning disable a  // CS1692 // Try this instad: // #pragma warning disable 1691 class A { static void Main() { } }  
```