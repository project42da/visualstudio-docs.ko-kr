---
title: ": Ca1813 파일을 봉인 되지 않은 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9ad548bd51985484ebcb39cb6022e994a5e0534a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: 봉인되지 않은 특성을 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidUnsealedAttributes|  
|CheckId|CA1813|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 공용 형식에서 상속 <xref:System.Attribute?displayProperty=fullName>는 추상 및 봉인 (`NotInheritable` Visual basic에서).  
  
## <a name="rule-description"></a>규칙 설명  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리는 사용자 지정 특성을 검색하는 메서드를 제공합니다. 기본적으로 이러한 메서드는 특성 상속 계층을 검색 예를 들어 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> 지정 된 특성 유형이 또는 지정된 된 특성 형식이 확장 하는 모든 특성 형식을 검색 합니다. 특성을 봉인 하면 상속 계층 구조 검색 하지 않으므로 성능을 향상 시킬 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하 고, 특성 형식을 봉인 또는 추상 확인 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 하면 특성 계층을 정의 하는 특성을 봉인 하거나 없습니다 abstract로 만들 경우에이 작업을 수행 해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는이 규칙을 만족 하는 사용자 지정 특성을 보여 줍니다.  
  
 [!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 [특성](/dotnet/standard/design-guidelines/attributes)