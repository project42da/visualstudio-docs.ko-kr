---
title: "컴파일러 오류 CS0685 | Microsoft Docs"
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
  - "CS0685"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0685"
ms.assetid: 20d7c6cf-a388-430f-b22b-232536912491
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0685
'member' 조건부 멤버에는 out 매개 변수를 사용할 수 없습니다.  
  
 메서드에서 <xref:System.Diagnostics.ConditionalAttribute> 특성을 사용하는 경우 해당 메서드에 out 매개 변수가 없을 수 있습니다. 이는 out 매개 변수에 사용된 변수의 값이 메서드 호출이 nothing으로 컴파일되는 경우 정의되지 않기 때문입니다. 이 오류를 방지하려면 조건부 메서드 선언에서 out 매개 변수를 제거하거나 조건부 특성을 사용하지 마세요.  
  
## 예제  
 다음 샘플에서는 CS0685를 생성합니다.  
  
```  
// CS0685.cs using System.Diagnostics; class C { [Conditional("DEBUG")] void trace(out int i)  // CS0685 { i = 1; } }  
```