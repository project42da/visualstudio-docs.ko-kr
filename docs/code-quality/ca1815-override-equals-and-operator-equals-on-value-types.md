---
title: "CA1815: 재정의 같음 및 값 형식에서 equals 또는 같음 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 927e13266bf308096592fb5714e1247f4b596ca8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하십시오.
|||  
|-|-|  
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|  
|CheckId|CA1815|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 공용 값 형식을 재정의 하지 않는 <xref:System.Object.Equals%2A?displayProperty=fullName>, 또는 같음 연산자 (= =)를 구현 하지 않습니다. 이 규칙에서 열거형을 확인 하지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 값 형식의 경우의 상속 된 구현 <xref:System.Object.Equals%2A> Reflection 라이브러리를 사용 하 고 모든 필드의 내용을 비교 합니다. Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다. 비교 또는 정렬할 경우 사용자가 자격 증명 또는 해시 테이블 키로 사용할 경우에 값 형식을 구현 해야 <xref:System.Object.Equals%2A>합니다. 프로그래밍 언어가 연산자 오버로드를 지원하는 경우 같음 및 같지 않음 연산자의 구현도 제공해야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면의 구현을 제공 <xref:System.Object.Equals%2A>합니다. 가능 하면 같음 연산자를 구현 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 값 형식의 인스턴스를 서로 비교 되지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
## <a name="example-of-a-violation"></a>위반의 예로  
  
### <a name="description"></a>설명  
 다음 예제에서는이 규칙을 위반 하는 구조 (값 형식)를 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]  
  
## <a name="example-of-how-to-fix"></a>수정 하는 방법의 예  
  
### <a name="description"></a>설명  
 다음 예제에서는 재정의 하 여 위반을 해결 <xref:System.ValueType.Equals%2A?displayProperty=fullName> 같음 연산자를 구현 하 고 (= =,! =) 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)  
  
 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object.Equals%2A?displayProperty=fullName>