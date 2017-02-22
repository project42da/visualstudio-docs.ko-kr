---
title: "CA2145: 투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다. | Microsoft Docs"
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
  - "CA2145"
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2145: 투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|  
|CheckId|CA2145|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.Security.SecuritySafeCriticalAttribute> 메서드로 표시된 또는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시된 메서드가 들어 있는 형식인 투명 메서드입니다.  
  
## 규칙 설명  
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 데코레이팅된 메서드에 이를 호출하는 메서드에 대한 암시적 LinkDemand가 배치되어 있습니다.  이 LinkDemand는 호출 코드가 보안을 중요시 하도록 요구합니다.  <xref:System.Security.SecurityCriticalAttribute> 특성이 있는 SuppressUnmanagedCodeSecurity를 사용하는 메서드를 표시하면 이 요구 사항을 메서드 호출자에 대해 더욱 명확하게 만들어줍니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드 또는 형식을 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
### 코드  
 [!code-cs[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]  
  
### 설명