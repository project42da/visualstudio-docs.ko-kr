---
title: "CA2142: 투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2142"
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# CA2142: 투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2142|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 투명 메서드는 <xref:System.Security.Permissions.SecurityAction> 또는 다른 보안 요청이 필요합니다.  
  
## 규칙 설명  
 이 규칙은 액세스하는 데 LinkDemands가 필요한 투명한 메서드에 적용됩니다.  보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다.  투명한 메서드는 보안 중립적으로 가정하기 때문에 이러한 모든 보안 결정을 내려서는 안 됩니다.  또한 보안 결정에 사용되는 안전한 중요 코드는 이전에 이러한 결정을 내리는 투명 코드를 사용해서는 안 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 투명한 메서드에서 링크 요구를 제거하거나 보안 요구 같은 보안 검사를 수행하는 경우 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 메서드를 표시하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서 메서드는 투명하고 <xref:System.Security.Permissions.SecurityAction>를 포함하는 LinkDemand <xref:System.Security.PermissionSet>로 표시되어 있기 때문에 규칙이 메서드에서 실행됩니다.  
  
 [!code-cs[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]  
  
 이 규칙에서는 경고를 표시해야 합니다.