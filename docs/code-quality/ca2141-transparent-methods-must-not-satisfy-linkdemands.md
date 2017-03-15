---
title: "CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2141"
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 14
---
# CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|  
|CheckId|CA2141|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 보안 투명 메서드는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\) 특성으로 표시된 어셈블리의 메서드를 호출하거나 보안 투명 메서드는 형식 또는 메서드에 대한 <xref:System.Security.Permissions.SecurityAction>`.LinkDemand`를 충족합니다.  
  
## 규칙 설명  
 LinkDemand 충족은 보안에 중요한 작업이며 의도하지 않게 권한이 높아질 수 있습니다.  보안에 중요한 코드와 같은 보안 감사 요구 사항이 적용되지 않기 때문에 보안 투명 코드는 LinkDemands를 충족해서는 안 됩니다.  보안 규칙 집합 수준 1 어셈블리의 투명 메서드는 모든 LinkDemands가 런타임에 전체 요구로 변환되기에 충분하여 성능 문제를 초래할 수 있습니다.  보안 규칙 집합 수준 2 어셈블리에서 투명한 메서드는 LinkDemand를 충족하는 경우 JIT\(Just\-In\-Time\) 컴파일러에서 컴파일할 수 없게 됩니다.  
  
 수준 2 보안을 사용하는 어셈블리에서 LinkDemand를 충족시키거나 비 APTCA 어셈블리에서 메서드를 호출하려고 보안 투명 메서드에 의한 시도는 <xref:System.MethodAccessException>을 발생시킵니다. 수준 1 어셈블리에서 LinkDemand는 완전 요청이 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙의 위반 문제를 해결하려면 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 액세스 메서드를 표시하거나 액세스된 메서드에서 LinkDemand를 제거하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 이 예제에서는 투명 메서드는 LinkDemand가 있는 메서드를 호출하려고 시도합니다.  이 규칙은 이 코드를 실행하지 않습니다.  
  
 [!code-cs[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]