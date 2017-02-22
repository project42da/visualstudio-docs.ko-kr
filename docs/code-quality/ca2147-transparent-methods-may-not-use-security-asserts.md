---
title: "CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다. | Microsoft Docs"
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
  - "SecurityTransparentCodeShouldNotAssert"
  - "CA2147"
  - "CA2128"
helpviewer_keywords: 
  - "CA2128"
  - "SecurityTransparentCodeShouldNotAssert"
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SecurityTransparentCodeShouldNotAssert|  
|CheckId|CA2147|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.Security.SecurityTransparentAttribute>로 표시된 코드에는 어설션하는 데 필요한 권한이 부여되지 않습니다.  
  
## 규칙 설명  
 이 규칙은 100% 투명하거나 투명\/중요가 혼합된 어셈블리의 모든 메서드와 형식을 분석하고 선언적이거나 명령적인 <xref:System.Security.CodeAccessPermission.Assert%2A>의 사용에 플래그를 지정합니다.  
  
 런타임에서 투명 코드의 <xref:System.Security.CodeAccessPermission.Assert%2A>에 대해 호출하면 <xref:System.InvalidOperationException>이 throw됩니다.  이런 현상은 100% 투명한 어셈블리 및 메서드나 형식이 투명하게 선언되었지만 선언적이거나 명령적인 어설션이 포함된 투명\/중요 혼합 어셈블리에서도 발생할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0에서는 *투명성*이라는 기능이 추가되었습니다.  개별 메서드, 필드, 인터페이스, 클래스 및 형식은 투명하거나 중요할 수 있습니다.  
  
 투명 코드에서 보안 권한을 상승시킬 수는 없습니다.  그러므로 부여되거나 요청된 권한이 코드를 통해 자동으로 호출자 또는 응용 프로그램 도메인에 전달됩니다.  권한 상승의 예로는 Asserts, LinkDemands, SuppressUnmanagedCode 및 `unsafe` 코드가 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 문제를 해결하려면 어설션을 <xref:System.Security.SecurityCriticalAttribute>로 호출하는 코드를 표시하거나 어설션을 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 메시지를 표시해야 합니다.  
  
## 예제  
 `Assert`  메서드가 <xref:System.InvalidOperationException>을 throw할 때 `SecurityTestClass`가 투명하면 이 코드가 실패합니다.  
  
 [!code-cs[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]  
  
## 예제  
 한 가지 옵션은 아래 예제에서 SecurityTransparentMethod 메서드의 코드를 검토하고 메서드가 권한 상승에 안전하다고 간주되는 경우 SecurityTransparentMethod를 보안에 중요한 것으로 표시합니다. 이렇게 하려면 어설션 하에서 이 메서드 내에서 발생하는 모든 호출과 함께 메서드에서 세부적이고 완전하고 오류가 없는 보안 감사를 수행해야 합니다.  
  
 [!code-cs[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]  
  
 다른 옵션은 코드에서 어설션을 제거하고 이후의 파일 I\/O 권한 요청이 SecurityTransparentMethod를 넘어 호출자에게 흐르도록 하는 것입니다.  이는 보안 검사를 활성화합니다.  일반적으로 권한 요청은 호출자 및\/또는 응용 프로그램 도메인으로 흐르기 때문에 이 경우에는 보안 감사가 필요하지 않습니다.  권한 요청은 보안 정책, 호스팅 환경 및 코드 소스 권한 부여를 통해 긴밀하게 제어됩니다.  
  
## 참고 항목  
 [보안 경고](../code-quality/security-warnings.md)