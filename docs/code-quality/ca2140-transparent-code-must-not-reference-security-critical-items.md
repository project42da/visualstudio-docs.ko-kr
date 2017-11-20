---
title: "CA2140: 투명 코드 보안에 중요 한 항목을 참조 하지 않아야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e11167ba35baf8802709d0d65b9b4045ede25126
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|  
|CheckId|CA2140|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 투명 메서드:  
  
-   보안에 중요 한 보안 예외 형식을 처리합니다.  
  
-   보안 중요 한 형식으로 표시 된 매개 변수  
  
-   보안 중요 한 제약 조건이 있는 제네릭 매개 변수  
  
-   보안 중요 형식의 지역 변수가 있습니다.  
  
-   로 표시 된 보안 중요 형식을 참조 합니다.  
  
-   로 표시 된 보안 중요 한 메서드 호출  
  
-   로 표시 된 보안 위험 필드 참조  
  
-   로 표시 된 보안 중요 형식을 반환합니다  
  
## <a name="rule-description"></a>규칙 설명  
 로 표시 된 코드 요소는 <xref:System.Security.SecurityCriticalAttribute> 특성은 보안에 중요 합니다. 투명 메서드는 보안에 중요한 요소를 사용할 수 없습니다. 투명 형식이 보안에 중요 한 형식을 사용 하려고 시도 하는 경우는 <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , 또는 <xref:System.FieldAccessException> 발생 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 다음 중 하나를 수행 합니다.  
  
-   표시 된 보안 중요 한 코드를 사용 하는 코드 요소는 <xref:System.Security.SecurityCriticalAttribute> 특성  
  
     \- 또는 -  
  
-   제거는 <xref:System.Security.SecurityCriticalAttribute> 중요 한 보안으로 표시 되 고으로 표시 하는 코드 요소에서 특성의 <xref:System.Security.SecuritySafeCriticalAttribute> 또는 <xref:System.Security.SecurityTransparentAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 투명 메서드는 보안에 중요 한 제네릭 컬렉션, 보안 중요 한 필드 및 보안 중요 한 메서드를 참조 하려고 합니다.  
  
 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityCriticalAttribute>   
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityTreatAsSafeAttribute>   
 <xref:System.Security?displayProperty=fullName>