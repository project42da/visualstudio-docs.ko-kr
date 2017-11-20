---
title: "CA2218: GetHashCode Equals를 재정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fa24be65377c563e6118fa99ab2983ee407874b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.
|||  
|-|-|  
|TypeName|OverrideGetHashCodeOnOverridingEquals|  
|CheckId|CA2218|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 공용 형식이 재정의 <xref:System.Object.Equals%2A?displayProperty=fullName> 하지만 재정의 하지 않습니다 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Object.GetHashCode%2A>해싱 알고리즘 및 해시 테이블과 같은 데이터 구조에 적합 하는 현재 인스턴스를 기반으로 하는 값을 반환 합니다. 동일한 형식이 고 동일한 두 개체는 다음 형식의 인스턴스가 올바르게 작동 하는지 확인 하는 동일한 해시 코드를 반환 해야 합니다.  
  
-   <xref:System.Collections.Hashtable?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>  
  
-   구현 하는 형식<xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면의 구현을 제공 <xref:System.Object.GetHashCode%2A>합니다. 구현 하는 경우 동일한 값을 반환 하는 확인 해야 동일한 유형의 개체를 쌍의 구현 <xref:System.Object.Equals%2A> 반환 `true` 쌍을 찾습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="class-example"></a>클래스 예제  
  
### <a name="description"></a>설명  
 다음 예제에서는이 규칙을 위반 하는 클래스 (참조 형식)를 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]  
  
### <a name="comments"></a>설명  
 다음 예제에서는 재정의 하 여 위반을 해결 <xref:System.Object.GetHashCode>합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]  
  
## <a name="structure-example"></a>구조 예제  
  
### <a name="description"></a>설명  
 다음 예제에서는이 규칙을 위반 하는 구조 (값 형식)를 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]  
  
### <a name="comments"></a>설명  
 다음 예제에서는 재정의 하 여 위반을 해결 <xref:System.Object.GetHashCode>합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Collections.Hashtable?displayProperty=fullName>   
 [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)