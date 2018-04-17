---
title: 'CA1000: 제네릭 형식에 대해 정적 멤버를 선언 하지 마십시오 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1000
- DoNotDeclareStaticMembersOnGenericTypes
helpviewer_keywords:
- DoNotDeclareStaticMembersOnGenericTypes
- CA1000
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc48a0f00e772648bd24758844450d58d461f031
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1000-do-not-declare-static-members-on-generic-types"></a>CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotDeclareStaticMembersOnGenericTypes|  
|CheckId|CA1000|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수는 제네릭 형식을 포함 한 `static` (`Shared` Visual basic에서) 멤버입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 경우는 `static` 제네릭 형식의 멤버 라고, 유형에 대 한 형식 인수를 지정 해야 합니다. 유추를 지원하지 않는 제네릭 인스턴스 멤버를 호출할 때는 멤버에 형식 인수를 지정해야 합니다. 이 두 가지 경우에 형식 인수를 지정 하기 위한 구문은 서로 다르며 혼동 되기 쉽습니다 다음 호출 하 여 설명한 것 처럼:  
  
```vb  
' Shared method in a generic type.  
GenericType(Of Integer).SharedMethod()  
  
' Generic instance method that does not support inference.  
someObject.GenericMethod(Of Integer)()  
```  
  
```csharp  
// Static method in a generic type.  
GenericType<int>.StaticMethod();  
  
// Generic instance method that does not support inference.  
someObject.GenericMethod<int>();  
```  
  
 일반적으로 이전 선언의 둘 다 형식 인수는 멤버 호출 될 때 지정 하지 않아도 되도록 사용 하지 마십시오. 이 구문에서 비 제네릭에 대 한 구문 다르지 않습니다 제네릭의 멤버를 호출에 대 한 결과입니다. 자세한 내용은 참조 [CA1004: 제네릭 메서드 형식 매개 변수를 제공 해야](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 정적 멤버를 제거 하거나 인스턴스 멤버를 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 제네릭을 사용 하 고 이해 하기 쉬운 구문 제공 더 많은 사용자가 새 라이브러리 및 학습에 걸리는 시간이 줄어듭니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)