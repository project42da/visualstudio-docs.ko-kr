---
title: "CA1411: COM 등록 메서드 표시 되지 않음을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67a4d4124ac1aae99327fdcd757db546cb50adfe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: COM 등록 메서드는 노출되면 안 됩니다.
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldNotBeVisible|  
|CheckId|CA1411|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 로 표시 된 메서드는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성은 외부에서 볼 수 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 어셈블리 구성 요소 개체 모델 (COM)으로 등록 되는 어셈블리의 각 COM 노출 형식에 대 한 레지스트리 항목이 추가 됩니다. 로 표시 된 메서드는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 및 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 특성 이라고 등록 및 등록 취소 프로세스는 동안 각각 이러한 형식의 등록/등록 취소에만 적용 되는 사용자 코드를 실행 합니다. 이 코드를이 프로세스 외부 호출 되어야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 메서드의 액세스 가능성 변경 `private` 또는 `internal` (`Friend` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 두 메서드를 보여 줍니다.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1410: COM 등록 메서드는 일치해야 합니다.](../code-quality/ca1410-com-registration-methods-should-be-matched.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [COM에 어셈블리 등록](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe(어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)