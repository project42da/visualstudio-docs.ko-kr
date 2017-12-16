---
title: "CA2134: 메서드 해야 일관성 있는 방식을 유지 기본 메서드를 재정의 하는 경우 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cfeadde26330273540d8d0b4ac00911905e9760e
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: 메서드는 기본 메서드를 재정의할 때 일관성 있는 방식을 유지해야 합니다.
|||  
|-|-|  
|TypeName|MethodsMustOverrideWithConsistentTransparency|  
|CheckId|CA2134|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 이 규칙은 표시 된 메서드는 <xref:System.Security.SecurityCriticalAttribute> 로 표시 되거나 투명 한 메서드는 <xref:System.Security.SecuritySafeCriticalAttribute>합니다. 규칙에는 또한로 표시 되거나 투명 한 메서드가 발생는 <xref:System.Security.SecuritySafeCriticalAttribute> 로 표시 된 메서드를 재정의 하는 <xref:System.Security.SecurityCriticalAttribute>합니다.  
  
 이 규칙은 가상 메서드를 재정의하거나 인터페이스를 구현할 때 적용됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙은 상속 체인 메서드의 보안 액세스 가능성을 변경 하려고 합니다. 예를 들어 기본 클래스의 가상 메서드 투명 하거나 안전에 중요 한 경우 다음 파생된 클래스 재정의 해야 투명 하거나 안전에 중요 한 메서드를 사용 합니다. 반대로, 보안에 중요 한 가상 인 경우 파생된 클래스 재정의 해야는 보안 중요 한 메서드로 합니다. 인터페이스 메서드를 구현 하는 것에 대 한 동일한 규칙이 적용 됩니다.  
  
 투명도 규칙 코드가 하면 대신 JIT 컴파일될 런타임에 투명도 계산은 동적 형식 정보를 보유 하지 않도록 적용 됩니다. 따라서 투명도 계산의 결과가 정적 형식을 JIT 컴파일되, 동적 형식에 관계 없이 전적으로 결정 될 수 있어야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 가상 메서드 또는 가상의 투명도 또는 인터페이스 메서드와 일치에 대 한 인터페이스를 구현 하는 방법의 투명도 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시 하지 마십시오. 이 규칙이 위반 될 런타임 <xref:System.TypeLoadException> 수준 2 투명도 사용 하는 어셈블리에 있습니다.  
  
## <a name="examples"></a>예제  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [보안 투명 코드, 수준 2](/dotnet/framework/misc/security-transparent-code-level-2)