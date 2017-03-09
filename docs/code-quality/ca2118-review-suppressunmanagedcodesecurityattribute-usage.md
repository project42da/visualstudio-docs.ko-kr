---
title: "CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2118"
  - "ReviewSuppressUnmanagedCodeSecurityUsage"
helpviewer_keywords: 
  - "CA2118"
  - "ReviewSuppressUnmanagedCodeSecurityUsage"
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|  
|CheckId|CA2118|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이나 멤버에 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 특성이 있습니다.  
  
## 규칙 설명  
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>는 COM interop 또는 플랫폼 호출을 사용하여 비관리 코드를 실행하는 멤버에 대한 기본 보안 시스템 동작을 변경합니다.  일반적으로 시스템은 비관리 코드 권한에 대한 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)를 만듭니다.  이 요청은 런타임에 멤버를 호출할 때마다 수행되며 호출 스택에 있는 모든 호출자의 권한을 검사합니다.  이 특성이 있으면 시스템은 권한에 대한 [링크 요청](../Topic/Link%20Demands.md)을 만듭니다. 호출자가 JIT로 컴파일된 경우 직접 실행 호출자의 권한을 검사합니다.  
  
 이 특성은 기본적으로 성능 향상을 위해 사용되지만 성능이 향상되는 대신 중대한 보안 위험이 발생합니다.  네이티브 메서드를 호출하는 public 멤버에 이 특성을 설정하면 호출 스택에 있는 직접 실행 호출자가 아닌 호출자는 비관리 코드 권한이 없어도 비관리 코드를 실행할 수 있습니다.  따라서 public 멤버의 작업과 입력 처리에 따라 보통은 신뢰할 수 있는 코드만 액세스할 수 있는 기능에 신뢰할 수 없는 호출자가 액세스할 수 있게 됩니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서는 보안 검사를 통해 호출자가 현재 프로세스의 주소 공간에 직접 액세스하지 못하도록 막습니다.  이 특성은 일반 보안을 우회하기 때문에 사용자 코드가 프로세스의 메모리를 읽고 쓰는 데 사용될 경우 심각한 보안 문제를 일으킬 수 있습니다.  고의적으로 프로세스 메모리에 대한 액세스를 제공하는 메서드만 위험한 것이 아닙니다. 악의적 코드가 잘못된 입력을 제공하는 등의 방법으로 액세스를 획득할 수 있는 모든 시나리오에 이러한 위험이 존재하게 됩니다.  
  
 기본 보안 정책에서는 어셈블리가 로컬 컴퓨터에서 실행되거나 다음 그룹 중 하나의 멤버인 경우 이외에는 어셈블리에 비관리 코드 권한을 부여하지 않습니다.  
  
-   내 컴퓨터 영역 코드 그룹  
  
-   Microsoft 강력한 이름 코드 그룹  
  
-   ECMA 강력한 이름 코드 그룹  
  
## 위반 문제를 해결하는 방법  
 코드를 신중하게 검토하여 이 특성이 꼭 필요한지 확인합니다.  관리 코드 보안에 익숙하지 않거나 이 특성을 사용할 경우의 보안 위험에 대해 잘 모를 경우에는 코드에서 이 특성을 제거하십시오.  이 특성이 꼭 필요한 경우 호출자가 코드를 악의적으로 사용하지 못하도록 해야 합니다.  코드에 비관리 코드를 실행할 권한이 없는 경우에는 이 특성이 아무런 효과가 없으므로 제거해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 안전하게 표시하지 않으려면 악용될 수 있는 작업이나 리소스에 대한 액세스 권한을 호출자에게 제공하지 못하도록 코드를 작성해야 합니다.  
  
## 예제  
 다음은 이 규칙을 위반하는 예제입니다.  
  
 [!code-cs[FxCop.Security.TypesDoNotSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_1.cs)]  
  
## 예제  
 다음 예제에서 `DoWork` 메서드는 플랫폼 호출 메서드인 `FormatHardDisk`에 공개적으로 액세스할 수 있는 코드 경로를 제공합니다.  
  
 [!code-cs[FxCop.Security.PInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_2.cs)]  
  
## 예제  
 다음 예제에서는 public 메서드인 `DoDangerousThing`에서 규칙을 위반합니다.  규칙 위반을 해결하려면 `DoDangerousThing`을 private으로 만들고 `DoWork` 메서드에서처럼 보안 요청으로 보안되는 public 메서드를 통해 액세스해야 합니다.  
  
 [!code-cs[FxCop.Security.TypeInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_3.cs)]  
  
## 참고 항목  
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>   
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [Security Optimizations](http://msdn.microsoft.com/ko-kr/cf255069-d85d-4de3-914a-e4625215a7c0)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)   
 [링크 요청](../Topic/Link%20Demands.md)