---
title: "CA2107: Deny 및 PermitOnly 사용을 검토하십시오. | Microsoft Docs"
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
  - "CA2107"
  - "ReviewDenyAndPermitOnlyUsage"
helpviewer_keywords: 
  - "ReviewDenyAndPermitOnlyUsage"
  - "CA2107"
ms.assetid: 366f4a56-ae93-4882-81d0-bd0a55ebbc26
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2107: Deny 및 PermitOnly 사용을 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewDenyAndPermitOnlyUsage|  
|CheckId|CA2107|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드에 PermitOnly 또는 Deny 보안 동작을 지정하는 보안 검사가 포함되어 있습니다.  
  
## 규칙 설명  
 [Using the PermitOnly Method](http://msdn.microsoft.com/ko-kr/8c7bdb7f-882f-45b7-908c-6cbaa1767649) 및 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName> 보안 동작은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 보안에 대해 잘 알고 있는 사용자만 사용해야 합니다.  이러한 보안 동작을 사용하는 코드는 보안 검토를 거쳐야 합니다.  
  
 Deny는 보안 요청에 대한 응답으로 수행되는 스택 워크의 기본 동작을 변경합니다.  이를 통해 호출 스택에 있는 호출자의 실제 권한에 관계없이 거부 메서드를 사용하는 동안 부여되지 않아야 할 권한을 지정할 수 있습니다.  스택 워크에서 Deny로 보안되는 메서드를 발견한 경우 요청된 권한이 거부된 권한에 포함되어 있으면 스택 워크가 실패합니다.  PermitOnly도 스택 워크의 기본 동작을 변경합니다.  즉, 호출자의 권한에 관계없이 코드에서 부여할 수 있는 권한만 지정할 수 있도록 허용합니다.  스택 워크에서 PermitOnly로 보안되는 메서드를 발견한 경우 요청된 권한이 PermitOnly로 지정된 권한에 포함되어 있지 않으면 스택 워크가 실패합니다.  
  
 이러한 동작을 사용하는 코드는 제한된 유용성과 미묘한 동작 때문에 보안 문제가 있는지 신중하게 검사해야 합니다.  다음을 살펴보십시오.  
  
-   [링크 요청](../Topic/Link%20Demands.md)은 Deny 또는 PermitOnly의 영향을 받지 않습니다.  
  
-   스택 워크를 발생시키는 요청과 같은 스택 프레임에서 Deny 또는 PermitOnly가 발생하면 보안 동작이 아무런 영향을 주지 않습니다.  
  
-   경로 기반 권한을 구성하는 데 사용되는 값은 일반적으로 여러 방법으로 지정할 수 있습니다.  경로의 한 형식에 대해 액세스를 거부하더라도 모든 형식에 대해 액세스가 거부되지는 않습니다.  예를 들어, 파일 공유 \\\\Server\\Share가 네트워크 드라이브 X:에 매핑된 경우 공유에 있는 파일에 대한 액세스를 거부하려면 \\\\Server\\Share\\File, X:\\File 및 파일에 액세스하는 다른 모든 경로를 거부해야 합니다.  
  
-   <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>는 Deny 또는 PermitOnly에 도달하기 전에 스택 워크를 종료시킬 수 있습니다.  
  
-   호출자에게 Deny에 의해 차단되는 권한이 있는 경우와 같이 Deny가 어떠한 영향을 미치는 경우 호출자는 Deny를 우회하여 보호된 리소스에 직접 액세스할 수 있습니다.  마찬가지로 호출자에게 거부되는 권한이 없는 경우 스택 워크는 Deny 없이 실패하기도 합니다.  
  
## 위반 문제를 해결하는 방법  
 이러한 보안 동작을 사용하면 위반이 발생합니다.  위반 문제를 해결하려면 이러한 보안 동작을 사용하지 마십시오.  
  
## 경고를 표시하지 않는 경우  
 보안 검토를 완료한 경우에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 Deny의 몇 가지 제한 사항을 보여 줍니다.  
  
 다음 라이브러리에는 해당 메서드를 보호하는 보안 요청 이외에는 동일한 두 개의 메서드가 있는 클래스가 들어 있습니다.  
  
 [!code-cs[FxCop.Security.PermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_1.cs)]  
  
## 예제  
 다음 응용 프로그램은 라이브러리에서 보안이 적용되는 메서드에 미치는 Deny의 영향을 보여 줍니다.  
  
 [!code-cs[FxCop.Security.TestPermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **요청: 호출자의 거부는 어설션된 권한이 있는 요청에는 영향을 미치지 않습니다.**  
**LinkDemand: 호출자의 거부는 어설션된 권한이 있는 LinkDemand에는 영향을 미치지 않습니다.**  
**LinkDemand: 호출자의 거부는 LinkDemand 보호 코드에는 영향을 미치지 않습니다.**  
**LinkDemand: 이 거부는 LinkDemand 보호 코드에는 영향을 미치지 않습니다.**   
## 참고 항목  
 <xref:System.Security.CodeAccessPermission.PermitOnly%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName>   
 <xref:System.Security.IStackWalk.PermitOnly%2A?displayProperty=fullName>   
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [Overriding Security Checks](http://msdn.microsoft.com/ko-kr/4acdeff5-fc05-41bf-8505-7387cdbfca28)   
 [Using the PermitOnly Method](http://msdn.microsoft.com/ko-kr/8c7bdb7f-882f-45b7-908c-6cbaa1767649)