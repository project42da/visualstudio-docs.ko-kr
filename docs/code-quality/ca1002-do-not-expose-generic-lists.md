---
title: 'CA1002: 제네릭 목록을 노출 하지 마십시오. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9aa12ea2d611d2e60e46665368b668e9c578db5b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002: 제네릭 목록을 노출하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotExposeGenericLists|  
|CheckId|CA1002|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 형식에 포함 되는 외부에서 볼 수 있는 멤버는 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 형식, 반환은 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 형식 또는 서명이 포함 되어는 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 매개 변수입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 상속이 아니라 성능을 위해 설계 되는 제네릭 컬렉션입니다. <xref:System.Collections.Generic.List%601?displayProperty=fullName> 보다 쉽게 상속된 된 클래스의 동작을 변경할 수 있도록 가상 멤버를 포함 되지 않습니다. 다음과 같은 제네릭 컬렉션 상속을 위해 디자인 하 고 대신 노출 되어야 합니다 <xref:System.Collections.Generic.List%601?displayProperty=fullName>합니다.  
  
-   <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 변경 된 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 형식 상속을 위해 디자인 된 제네릭 컬렉션 중 하나입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 경고를 발생 시킨 어셈블리 재사용 가능한 라이브러리를 다루지는지 않습니다 하지 않는 한이 규칙에서는 경고를에서 표시 하지 마십시오. 예를 들어 것 성능 조정 된 응용 프로그램에서이 경고를 표시 하지 않아도 안전 하 게 제네릭 목록 사용 하는 성능상의 이점을 얻은 위치.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)