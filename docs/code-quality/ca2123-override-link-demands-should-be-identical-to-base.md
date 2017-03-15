---
title: "CA2123: 재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2123"
  - "OverrideLinkDemandsShouldBeIdenticalToBase"
helpviewer_keywords: 
  - "CA2123"
  - "OverrideLinkDemandsShouldBeIdenticalToBase"
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2123: 재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|  
|CheckId|CA2123|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 public 형식의 public 또는 protected 메서드가 메서드를 재정의하거나 인터페이스를 구현하고 이 메서드의 [링크 요청](../Topic/Link%20Demands.md)이 인터페이스 또는 가상 메서드의 링크 요청과 같지 않습니다.  
  
## 규칙 설명  
 이 규칙에서는 메서드를 다른 형식의 인터페이스이거나 가상 메서드인 기본 메서드에 일치시킨 다음 각각에 대해 링크 요청을 비교합니다.  메서드와 기본 메서드 중 하나에만 링크 요청이 있고 나머지 다른 하나에는 링크 요청이 없는 경우 위반이 보고됩니다.  
  
 이 규칙이 위반된 경우 악의적인 호출자가 보안상 위험한 메서드를 호출하여 링크 요청을 우회할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 같은 링크 요청을 재정의 메서드 또는 구현에 적용합니다.  가능하지 않은 경우 전체 요청으로 메서드를 표시하거나 특성을 완전히 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙이 위반되는 다양한 형태를 보여 줍니다.  
  
 [!code-cs[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]  
  
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [링크 요청](../Topic/Link%20Demands.md)