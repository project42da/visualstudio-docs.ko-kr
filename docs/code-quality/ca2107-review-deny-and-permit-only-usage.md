---
title: 'CA2107: 검토 deny 및 permitonly 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2107
- ReviewDenyAndPermitOnlyUsage
helpviewer_keywords:
- ReviewDenyAndPermitOnlyUsage
- CA2107
ms.assetid: 366f4a56-ae93-4882-81d0-bd0a55ebbc26
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1d8eb2b3cda2684dbae218d10abc7594b6f5f55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2107-review-deny-and-permit-only-usage"></a>CA2107: Deny 및 PermitOnly 사용을 검토하십시오.
|||  
|-|-|  
|TypeName|ReviewDenyAndPermitOnlyUsage|  
|CheckId|CA2107|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Deny 또는 PermitOnly 보안 동작을 지정 하는 보안 검사를 포함 하는 메서드입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName> 잘된 알고 있는 사용자에 게 의해서만 보안 동작을 사용 해야의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 보안 합니다. 이러한 보안 동작을 사용하는 코드는 보안 검토를 거쳐야 합니다.  
  
 거부 하는 보안 요청에 대 한 응답에서 발생 하는 스택 워크의 기본 동작을 변경 합니다. 호출 스택의 호출자의 실제 권한에 상관 없이 거부 메서드 중에 부여 되지 않아야 하는 권한을 지정할 수 있습니다. 스택 워크 Deny로 보호 되는 메서드를 검색 하 고 요청 된 권한이 거부 된 권한에 포함 하는 경우에 스택 워크 실패 합니다. 또한 PermitOnly는 스택 워크의 기본 동작을 변경합니다. 코드를에서 호출자의 권한에 관계 없이 부여할 수 있는 권한만 지정할 수 있습니다. 스택 워크 PermitOnly로 보호 되는 메서드를 검색 하 고 있는 것은 아니며는 PermitOnly에서 지정 된 사용 권한에 포함 되지 않은, 스택 워크가 실패 합니다.  
  
 제한 된 유용성 및 미묘한 동작으로 인해 보안 취약점에 대해 이러한 동작을 사용 하는 코드를 신중 하 게 평가 되어야 합니다. 다음을 살펴보세요.  
  
-   [링크 요구](/dotnet/framework/misc/link-demands) Deny 또는 PermitOnly 영향을 받지 않습니다.  
  
-   Deny 또는 PermitOnly에는 스택 워크를 발생 시키는 요청과 같은 스택 프레임에서 발생 하는 경우 보안 동작 아무런 효과가 없습니다.  
  
-   일반적으로 여러 가지 방법으로 경로 기반 권한을 구성 하는 데 사용 되는 값을 지정할 수 있습니다. 한 가지 형태의 경로에 대 한 액세스를 거부 모든 폼에 대 한 액세스를 거부 하지 않습니다. 예를 들어 파일 공유 \\거부 해야 \Server\Share 매핑된 네트워크 드라이브는 공유에서 파일에 대 한 액세스를 거부 하려면 x:에 \\\Server\Share\File, X:\File 및 파일에 액세스 하는 다른 모든 경로입니다.  
  
-   <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> Deny 또는 PermitOnly에 도달 하기 전에 스택 워크를 종료할 수 있습니다.  
  
-   Deny에 영향을 줄 경우 즉, 사용 권한을 Deny에 의해 차단 되는 경우 호출자에 게 우회 액세스할 수 있습니다 보호 되는 리소스를 직접 거부 합니다. 마찬가지로, 호출자에 게 거부 된 사용 권한이 없습니다 스택 워크는 Deny 없이 못합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이러한 보안 동작을 사용 하면 위반이 발생 합니다. 위반 문제를 해결 하려면 이러한 보안 동작을 사용 하지 마십시오.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 보안 검토를 완료 한 후에이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 몇 가지 제한 사항이 deny 보여 줍니다.  
  
 다음 라이브러리는 보호 하는 보안 요구 사항 이외에 동일한 두 메서드가 있는 클래스를 포함 합니다.  
  
 [!code-csharp[FxCop.Security.PermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_1.cs)]  
  
## <a name="example"></a>예제  
 다음 응용 프로그램 라이브러리에서 Deny의 보안이 유지 되는 방법에 영향을 보여 줍니다.  
  
 [!code-csharp[FxCop.Security.TestPermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **요청: 호출자의 Deny는 어설션된 사용 권한이 있는 주문형 효과가 없습니다.**  
**LinkDemand: 호출자의 거부 된 어설션된 권한 LinkDemand에 영향을 주지에 있습니다.**  
**LinkDemand: 호출자의 Deny가 LinkDemand로 보호 된 코드로 영향을 주지 않습니다.**  
**LinkDemand:이 Deny가 LinkDemand로 보호 된 코드로 영향을 주지 않습니다.**   
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.CodeAccessPermission.PermitOnly%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName>   
 <xref:System.Security.IStackWalk.PermitOnly%2A?displayProperty=fullName>   
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   

