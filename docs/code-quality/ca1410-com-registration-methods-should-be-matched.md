---
title: "CA1410: COM 등록 메서드는 일치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 65c6191aff1433d050c1f7b50097c88d1d3cf2a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM 등록 메서드는 일치해야 합니다.
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldBeMatched|  
|CheckId|CA1410|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 형식으로 표시 된 메서드를 선언는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성으로 표시 된 메서드를 선언 하지 않는 있지만 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성 또는 그 반대로 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 만들려는 구성 요소 개체 모델 (COM) 클라이언트에 대 한 한 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식 형식을 등록 해야 합니다. 를 사용할 수 있는 경우로 표시 된 메서드는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 특성 사용자 지정 코드를 실행 하는 등록 과정 동안 호출 됩니다. 로 표시 된 해당 메서드는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 등록 메서드의 작업을 되돌리기 위해 등록 프로세스 동안 이라고 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 해당 등록 또는 등록 취소 메서드를 추가 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다. 주석 처리 된 코드는 위반에 대 한 해결 방법을 보여 줍니다.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1411: COM 등록 메서드는 노출되면 안 됩니다.](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [COM에 어셈블리 등록](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe(어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)