---
title: "CA1018: 표시 특성을 AttributeUsageAttribute로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2b94cb7c11c803e713609036db12c47e2027cb61
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.
|||  
|-|-|  
|TypeName|MarkAttributesWithAttributeUsage|  
|CheckId|CA1018|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 <xref:System.AttributeUsageAttribute?displayProperty=fullName> 특성을 사용자 지정 특성에 나타나지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 사용자 지정 특성을 정의할 때 사용 하 여 표시할 <xref:System.AttributeUsageAttribute> 소스 코드에서 사용자 지정 특성을 적용할 수 있습니다 위치를 나타냅니다. 특성의 의미 및 용도에 따라 코드에서의 유효한 위치가 결정됩니다. 예를 들어 누가 유지 관리 하 고 라이브러리에서 각 형식 향상 이며 책임 형식 수준에서 항상 할당 된 사용자를 식별 하는 특성을 정의할 수 있습니다. 이 경우 컴파일러는 특성 클래스, 열거형 및 인터페이스를 사용 하도록 설정 해야 하지만 메서드, 이벤트 또는 속성에 허용 하지 마십시오. 어셈블리에서 특성을 사용할 수 있어야 하는지 여부를 조직 구성 정책 및 절차에 따라 결정 됩니다.  
  
 <xref:System.AttributeTargets?displayProperty=fullName> 열거형을 사용자 지정 특성에 대해 지정할 수 있는 대상을 정의 합니다. 생략 하면 <xref:System.AttributeUsageAttribute>, 사용자 지정 특성에 정의 된 대로 모든 대상에 대해 유효 하지 됩니다는 `All` 값 <xref:System.AttributeTargets> 열거 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 사용 하 여 특성에 대 한 대상을 지정 <xref:System.AttributeUsageAttribute>합니다. 다음 예제를 참조하세요.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 메시지를 제외 하는 대신이 규칙 위반 문제를 해결 해야 합니다. 특성을 상속 하는 경우에 <xref:System.AttributeUsageAttribute>, 코드 유지 관리를 간소화 하는 특성이 있어야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 가지 특성을 정의합니다. `BadCodeMaintainerAttribute`생략 된 올바르지 않은 <xref:System.AttributeUsageAttribute> 문, 및 `GoodCodeMaintainerAttribute` 올바르게이 단원의 앞에서 설명한 특성을 구현 합니다. 속성 `DeveloperName` 설계 규칙에 필요한 [CA1019: 특성 인수의 접근자를 정의](../code-quality/ca1019-define-accessors-for-attribute-arguments.md) 완전성을 위해 포함 됩니다.  
  
 [!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>참고 항목  
 [특성](/dotnet/standard/design-guidelines/attributes)