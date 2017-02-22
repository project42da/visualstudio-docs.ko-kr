---
title: "CA2146: 형식은 최소한 기본 형식 및 인터페이스만큼 중요해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2146"
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2146: 형식은 최소한 기본 형식 및 인터페이스만큼 중요해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|  
|CheckId|CA2146|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 투명 형식은 <xref:System.Security.SecuritySafeCriticalAttribute> 또는 <xref:System.Security.SecurityCriticalAttribute>로 표시된 형식 또는 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시된 형식에서 파생된 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시된 형식에서 파생됩니다.  
  
## 규칙 설명  
 이 규칙은 파생 형식에 기본 형식 또는 구현된 인터페이스만큼 중요하지 않은 보안 투명성 특성이 있을 때 적용됩니다.  중요한 기본 형식에서 파생되거나 중요한 인터페이스를 구현할 수 있는 것은 중요한 형식뿐이고, 안전에 중요한 기본 형식에서 파생되거나 안전에 중요한 인터페이스를 구현할 수 있는 것은 중요하거나 안전에 중요한 형식뿐입니다.  수준 2 투명성에서 이 규칙 위반은 파생된 형식에 대한 <xref:System.TypeLoadException>에서 발생합니다.  
  
## 위반 문제를 해결하는 방법  
 이 위반 문제를 해결하려면 파생되거나 구현 중인 형식을 최소한 기본 형식 또는 인터페이스만큼 중요한 투명도 특성으로 표시하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 [!code-cs[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]