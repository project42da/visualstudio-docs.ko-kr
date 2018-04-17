---
title: 'CA2151: 중요 한 형식으로 필드 보안에 중요 해야 합니다 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1123b3a2d73119836265dcf1dd4dcdc763179ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: 중요한 형식이 포함된 필드는 보안에 중요한 필드여야 함
|||  
|-|-|  
|TypeName||  
|CheckId|CA2151|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 보안 투명 필드 또는 안전 중요 필드가 선언되었습니다. 해당 형식은 보안에 중요한 것으로 지정되었습니다. 예:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      Type1 m_field; // CA2151, transparent field of critical type  
   }  
  
```  
  
 이 예제에서 `m_field`는 보안 중요 형식의 보안 투명 필드입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 보안 중요 형식을 사용하려면 이 형식을 참조하는 코드가 보안 중요 또는 보안 안전 중요여야 합니다. 참조가 간접적인 경우에도 마찬가지입니다. 예를 들어, 중요 형식이 있는 투명 필드를 참조할 경우 코드는 보안 중요 또는 보안 안전이어야 합니다. 따라서 투명 코드는 필드에 액세스할 수 없으므로 보안 투명 또는 보안 안전 중요 필드가 있을 경우 잘못 해석됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반을 해결하려면 필드에 <xref:System.Security.SecurityCriticalAttribute> 특성을 표시하거나 보안 투명 또는 안전 중요 필드가 참조하는 형식을 만듭니다.  
  
```csharp  
// Fix 1: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
// Fix 2: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   class Type1 { } // Type1 is now transparent  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
```  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2151-fields-with-critical-types-should-be-security-critical_1.cs)]  
  
### <a name="comments"></a>설명