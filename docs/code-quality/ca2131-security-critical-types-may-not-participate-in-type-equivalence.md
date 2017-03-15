---
title: "CA2131: 보안에 중요한 형식은 형식 등가에 참여할 수 없습니다. | Microsoft Docs"
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
  - "CA2131"
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2131: 보안에 중요한 형식은 형식 등가에 참여할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|  
|CheckId|CA2131|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 형식 등가에 참가하는 형식 및 형식 자체 또는 멤버나 형식의 필드는 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시됩니다.  
  
## 규칙 설명  
 이 규칙은 중요한 형식 또는 중요한 메서드나 필드를 포함하는 형식이 형식 동등에 참여하는 경우에 적용됩니다.  CLR이 이러한 형식을 감지하면 런타임에서 <xref:System.TypeLoadException>과 함께 로드에 실패합니다.  일반적으로 이 규칙은 사용자가 tlbimp와 컴파일러를 이용하여 형식 동등을 수행하지 않고 수동으로 형식 동등을 구현하는 경우에만 적용됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 SecurityCritical 특성을 제거하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 실행시키는 인터페이스, 메서드 및 필드를 보여줍니다.  
  
 [!code-cs[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]  
  
## 참고 항목  
 [보안 투명 코드, 수준 2](../Topic/Security-Transparent%20Code,%20Level%202.md)