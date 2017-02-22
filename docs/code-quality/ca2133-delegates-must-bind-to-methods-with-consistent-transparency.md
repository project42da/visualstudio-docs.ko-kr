---
title: "CA2133: 대리인은 투명도가 일관된 메서드에 바인딩해야 합니다. | Microsoft Docs"
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
  - "CA2133"
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2133: 대리인은 투명도가 일관된 메서드에 바인딩해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DelegatesMustBindWithConsistentTransparency|  
|CheckId|CA2133|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
> [!NOTE]
>  이 경고는 CoreCLR\(Silverlight 웹 응용 프로그램에 특정한 CLR 버전\)을 실행하는 코드에만 적용됩니다.  
  
## 원인  
 이 경고는 <xref:System.Security.SecurityCriticalAttribute>로 표시된 대리자를 투명하거나 <xref:System.Security.SecuritySafeCriticalAttribute>로 표시된 메서드에 바인딩하는 메서드에서 실행됩니다.  또한 투명하거나 안전에 중요한 대리자를 중요한 메서드에 바인딩하는 메서드에서도 이 경고가 발생합니다.  
  
## 규칙 설명  
 바인딩되는 대리자 형식 및 메서드는 투명도가 일관성이 있어야 합니다.  투명하고 보안에 중요한 대리자는 투명하거나 보안에 중요한 다른 메서드에만 바인딩할 수 있습니다.  마찬가지로 중요한 대리자는 중요한 메서드에만 바인딩할 수 있습니다.  이러한 바인딩 규칙은 대리자를 통해 메서드를 호출할 수 있는 코드만 같은 메서드를 직접 호출할 수 있는지 확인합니다.  예를 들어, 바인딩 규칙은 투명 코드가 투명한 대리자를 통해 직접 중요한 코드를 호출하는 것을 방지합니다.  
  
## 위반 문제를 해결하는 방법  
 이 경고 위반 문제를 해결하려면 둘의 투명도가 동등해지도록 대리자 또는 메서드의 투명도를 변경하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
### 코드  
 [!code-cs[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]