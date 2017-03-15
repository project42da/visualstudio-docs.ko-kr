---
title: "CA2138: 투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다. | Microsoft Docs"
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
  - "CA2138"
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2138: 투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|  
|CheckId|CA2138|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 보안 투명 메서드는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시된 메서드를 호출합니다.  
  
## 규칙 설명  
 이 규칙은 P\/Invoke\(플랫폼 호출\) 호출을 통해 사용함으로써 네이티브 코드로 직접 호출하는 모든 투명 메서드에서 실행됩니다.  <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시되는 P\/Invoke 및 COM interop 메서드는 호출하는 메서드에 대해 LinkDemand가 실행되도록 합니다.  보안 투명 코드가 LinkDemands를 충족할 수 없기 때문에 코드는 SuppressUnmanagedCodeSecurity 특성이 표시된 메서드 또는 SuppressUnmanagedCodeSecurity 특성이 표시된 클래스의 메서드를 호출할 수 없습니다.  이 메서드는 실패하거나 요청이 완전 요청으로 변환됩니다.  
  
 이 규칙 위반으로 인해 수준 2 보안 투명성 모델에서 <xref:System.MethodAccessException>이 발생하고 수준 1 투명성 모델에서 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>에 대한 완전 요청이 발생합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성을 제거하고 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 이 메서드를 표시하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 [!code-cs[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]