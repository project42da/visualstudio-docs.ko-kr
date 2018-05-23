---
title: 'CA1032: 표준 예외 생성자를 구현하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6cd6922cae5e2d182a279e2d1637a19f8572468
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032: 표준 예외 생성자를 구현하십시오.

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식 확장 <xref:System.Exception?displayProperty=fullName> 그러나 모든 필수 생성자를 선언 하지 않습니다.

## <a name="rule-description"></a>규칙 설명

예외 형식에는 다음 세 명의 생성자 구현 해야 합니다.

- 공용 NewException()

- 공용 NewException(string)

- 공용 NewException (문자열, 예외)

또한으로 레거시 FxCop 정적 코드 분석을 실행 하는 경우와 반대 [Roslyn 기반 FxCop 분석기](../code-quality/roslyn-analyzers-overview.md), 없는 경우 네 번째 생성자 또한 위반을 생성 합니다.

- protected 또는 private NewException (SerializationInfo, StreamingContext)

이들 생성자 집합을 전부 제공하지 못하면 예외를 제대로 처리하기 어려울 수 있습니다. 예를 들어는 서명이 있는 생성자 `NewException(string, Exception)` 다른 예외로 인해 발생 하는 예외를 만드는 데 사용 됩니다. 이 생성자가 없는 없습니다 만들고은 관리 되는 코드는 이러한 상황에서 수행 해야 하는 내부 (중첩 된) 예외를 포함 하 여 사용자 지정 예외의 인스턴스를 throw 합니다.

첫 번째 세 가지 예외 생성자는 규칙에 따라 공용입니다. 네 번째 생성자는 unsealed 클래스에서 보호 되어 봉인된 클래스에서 private입니다. 자세한 내용은 참조 [CA2229: serialization 생성자를 구현](../code-quality/ca2229-implement-serialization-constructors.md)

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

이 규칙 위반 문제를 해결 하려면 누락 된 생성자는 예외에 추가 하 고 올바른 액세스 가능성 있는지 확인 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

Public 생성자에 대 한 다른 액세스 수준을 사용 하 여 위반이 발생 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 또한에 대 한 경고를 표시 하지 않는 있어도 됩니다는 `NewException(SerializationInfo, StreamingContext)` 생성자는 PCL 이식 가능한 클래스 라이브러리 ()를 작성 하는 경우.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반 하는 예외 유형 및 제대로 구현 되는 예외 유형을 포함 합니다.

[!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]

## <a name="see-also"></a>참고자료

[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)