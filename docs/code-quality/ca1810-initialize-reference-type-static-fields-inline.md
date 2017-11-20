---
title: "CA1810: 참조 형식 정적 필드를 인라인으로 초기화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 113d5206d2b4827902cf83827efd5b8738387755
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오.
|||  
|-|-|  
|TypeName|InitializeReferenceTypeStaticFieldsInline|  
|CheckId|CA1810|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 참조 형식에서 명시적인 정적 생성자를 선언합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 형식이 명시적인 정적 생성자를 선언하면 JIT(Just-in-Time) 컴파일러는 형식의 각 정적 메서드와 인스턴스 생성자에 검사를 추가하여 정적 생성자를 이전에 호출했는지 확인합니다. 정적 초기화 된 형식의 인스턴스를 만들 때 또는 정적 멤버에 액세스 하는 경우 트리거됩니다. 그러나 형식의 변수를 선언 하지만 사용 하지 않는 것을 초기화 하는 전역 상태를 변경 하는 경우에 중요 수 하는 경우 정적 초기화 트리거되지 않습니다.  
  
 모든 정적 데이터를 인라인으로 초기화 하 고 명시적인 정적 생성자 선언 되지 않은 Microsoft MSIL (intermediate language) 컴파일러 추가 `beforefieldinit` 플래그 및 MSIL 형식에 정적 데이터를 초기화 하는 암시적 정적 생성자 정의 합니다. JIT 컴파일러에서 발생 하는 경우는 `beforefieldinit` 플래그를 대부분의 경우 정적 생성자 검사 추가 되지 않습니다. 정적 초기화는 정적 메서드 또는 인스턴스 생성자가 호출 되기 전에 하지 않지만 정적 필드에 액세스 하기 전에 약간의 시간이 발생 하도록 보장 됩니다. Note 하는 형식의 변수가 선언 된 후 언제 든 지 발생할 수 있습니다.  
  
 정적 생성자 검사로 인해 성능이 저하될 수 있습니다. 정적 생성자는 종종 초기화만 있는지 확인 해야 하는 경우 정적 필드의 첫 번째 액세스 하기 전에 발생 하는 정적 필드에만 사용 됩니다. `beforefieldinit` 동작은 이러한 및 대부분의 다른 형식에 적합 합니다. 경우에 없습니다만 적절 한 경우 다음 중 하나 및 정적 초기화의 글로벌 상태에 영향을 줍니다.  
  
-   전역 상태에 대 한 영향 상당히 소모 되며 형식을 사용 하지 않는 경우 필요 하지 않습니다.  
  
-   형식의 정적 필드에 액세스 하지 않고 전역 상태 정보를 액세스할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 안전 성능이; 별로 중요 하지 않은 경우이 규칙에서 경고를 표시 합니다. 정적 초기화가 발생 하는 전역 상태 변경 내용을 비용이 많이 드는 또는 해야 하는 경우 또는 형식의 정적 메서드를 호출 하거나 형식의 인스턴스를 만들 전에 적용 되려면 보장할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 형식 `StaticConstructor`, 규칙을 위반 하는 형식이 있는 `NoStaticConstructor`, 인라인 초기화가 규칙을 만족 하 고 정적 생성자를 대체 하 합니다.  
  
 [!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/CSharp/ca1810-initialize-reference-type-static-fields-inline_1.cs)]
 [!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/VisualBasic/ca1810-initialize-reference-type-static-fields-inline_1.vb)]  
  
 추가 `beforefieldinit` 플래그에 대 한 MSIL 정의에 `NoStaticConstructor` 클래스입니다.  
  
 **ansi 자동으로 공용.class StaticConstructor**  
 **[mscorlib]System.Object 확장**  
**{**  
**} / 끝 / StaticConstructor 클래스**  
**.class 공용 자동 ansi beforefieldinit NoStaticConstructor**  
 **[mscorlib]System.Object 확장**  
**{**  
**} / 끝 / NoStaticConstructor 클래스**   
## <a name="related-rules"></a>관련된 규칙  
 [CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오.](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)