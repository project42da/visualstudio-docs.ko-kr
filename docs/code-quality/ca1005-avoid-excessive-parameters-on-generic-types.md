---
title: ": Ca1005 파일을 제네릭 형식에 매개 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3bbf8dae17c9f0fd257388d8520485bf1a5d6970
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidExcessiveParametersOnGenericTypes|  
|CheckId|CA1005|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 제네릭 형식이 형식 매개 변수를 두 개 이상의 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 제네릭 형식에 포함된 형식 매개 변수가 많을수록 각 형식 매개 변수가 무엇을 나타내는지를 파악하거나 기억하기가 더 어렵습니다. 보통은 다음과 같이 하나의 형식 매개 변수 `List<T>`, 고 다음과 같이 두 개의 형식 매개 변수가 있는 일부 경우에 `Dictionary<TKey, TValue>`합니다. 형식 매개 변수가 세 개 이상의 경우는 너무 어렵습니다 대부분의 사용자 (예를 들어 `TooManyTypeParameters<T, K, V>` C# 또는 `TooManyTypeParameters(Of T, K, V)` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 두 개의 형식 매개 변수를 사용 하도록 디자인을 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 디자인에 두 개 이상의 형식 매개 변수가 반드시 필요한 경우가 아니면이 규칙에서는 경고를에서 표시 하지 마십시오. 제네릭을 사용 하 고 이해 하기 쉬운 구문 제공 더 많은 사용자가 새 라이브러리 및 학습에 걸리는 시간이 줄어듭니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)