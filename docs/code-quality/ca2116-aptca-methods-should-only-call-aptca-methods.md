---
title: "CA2116: APTCA 메서드는 APTCA 메서드만 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a3a7818c3d758e8e92724af37dfe955f9a466746
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.
|||  
|-|-|  
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|  
|CheckId|CA2116|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 가진 어셈블리의 메서드는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 어셈블리에는 특성이 있는 메서드를 호출 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 기본적으로 강력한 이름의 어셈블리의 public 또는 protected 메서드에 의해 보호 암시적으로 되는 [링크 요청](/dotnet/framework/misc/link-demands) 완전 신뢰에만 완전히 신뢰할 수 있는 호출자 강력한 이름의 어셈블리에 액세스할 수 있습니다. 강력한 이름의 어셈블리는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA)이이 보호 필요가 없습니다. 특성 사용 어셈블리를 인트라넷 또는 인터넷에서을 실행 하는 코드와 같은 완전 신뢰를 갖지 않는 호출자에 게 액세스할 수 있도록 하는 링크 요청을 하지 않습니다.  
  
 완전히 신뢰할 수 있는 어셈블리에 APTCA 특성이 부분적으로 신뢰할 수 있는 호출자를 허용 하지 않는 다른 어셈블리의 코드를 실행 하는 경우 보안 허점이 불가능 합니다. 하는 경우 두 가지 방법 `M1` 및 `M2` 다음 조건을 충족, 악의적인 호출자가 메서드를 사용할 수 `M1` 를 보호 하는 완전 신뢰 암시적 링크 요청을 사용 하지 않을 `M2`:  
  
-   `M1`공용 메서드는 APTCA 특성이 있는 완전히 신뢰할 수 있는 어셈블리에 선언 됩니다.  
  
-   `M1`메서드를 호출 `M2` 외부 `M1`의 어셈블리.  
  
-   `M2`어셈블리에 APTCA 특성이 없고, 따라서 실행 하지 않아야 또는 부분적으로 신뢰할 수 있는 호출자를 대신 하 여 합니다.  
  
 부분적으로 신뢰할 수 있는 호출자 `X` 메서드를 호출할 수 `M1`이며, `M1` 호출할 `M2`합니다. 때문에 `M2` APTCA 특성이, 직접 호출자 (`M1`) 완전 신뢰에 대 한 링크 요청을 충족 해야 합니다 `M1` 완전 신뢰를 포함 하 고 따라서이 검사를 충족 합니다. 보안 위험 때문에 `X` 만족 보호 하는 링크 요청에 참여 하지 않는 `M2` 신뢰할 수 없는 호출자 로부터 합니다. 따라서 APTCA 특성이 있는 메서드에 특성이 없는 메서드 호출 해서는 안 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 APCTA 특성이 필요한 경우 완전 신뢰 어셈블리를 호출 하는 메서드를 보호 하는 요청을 사용 합니다. 요구가 메서드에서 노출 하는 기능에 따라 달라 집니다 정확한 권한입니다. 가능한 경우 기본 기능이 부분적으로 신뢰할 수 있는 호출자에 게 노출 되지 않도록 하려면 완전 신뢰에 대 한 요청으로 메서드를 보호 합니다. 없는 경우는 노출 된 기능을 효과적으로 보호 하는 사용 권한 집합을 선택 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를에서 표시 하지 않으려면, 메서드에서 노출 하는 기능이을 직접 또는 간접적으로 허용 하지 호출자가 중요 한 정보, 작업 또는 악용에서 사용할 수 있는 리소스에 액세스 하도록 확인 해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 어셈블리와 테스트 응용 프로그램을 사용 하 여이 규칙으로 검색 하는 보안 문제를 나타냅니다. 첫 번째 어셈블리에 APTCA 특성이 없고 부분적으로 신뢰할 수 있는 호출자에 게 액세스할 수 없습니다 (나타내는 `M2` 이전 설명의).  
  
 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]  
  
## <a name="example"></a>예  
 두 번째 어셈블리는 완전히 신뢰할 수 있는 이며 부분적으로 신뢰할 수 있는 호출자를 허용 합니다. (나타내는 `M1` 이전 설명의).  
  
 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]  
  
## <a name="example"></a>예  
 테스트 응용 프로그램 (나타내는 `X` 이전 설명의) 부분적으로 신뢰할 수 있습니다.  
  
 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **완전 신뢰: 요청에 대 한 요청에 실패 했습니다.**  
**ClassRequiringFullTrust.DoWork 호출 되었습니다.**   
## <a name="related-rules"></a>관련된 규칙  
 [CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   
 [부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)   
 [링크 요구](/dotnet/framework/misc/link-demands)   
 [데이터 및 모델링](/dotnet/framework/data/index)