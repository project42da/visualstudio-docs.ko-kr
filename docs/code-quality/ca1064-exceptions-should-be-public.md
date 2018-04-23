---
title: 'CA1064: 예외는 public이어야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 73daa2d834342cf9d4759d569cd637661696e34d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: 예외는 public이어야 합니다.
|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public이 아닌 예외에서 직접 파생 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="rule-description"></a>규칙 설명
 만 내부 예외는 내부 범위 내에 표시 됩니다. 예외가 내부 범위 밖에 놓이게 되면 예외를 catch하는 데 기본 예외만 사용할 수 있습니다. 내부 예외가 상속 되 면 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>, 외부 코드의 예외와 수행할 작업을 이해 하는 데 충분 한 정보가 체계가 없습니다.

 하지만 코드는 나중에 사용 되는 기준으로 내부 예외에 대 한 공용 예외 있으면이 코드를 더 자세히 아웃 있을 것으로 가정 기본 예외 인텔리전트 수행할 수 있게 합니다. 공용 예외에서 제공 하는 것 보다 더 많은 정보 갖습니다 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 예외 공용으로 만들거나 내부 예외가 아닌 공용 예외에서 파생 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 모든 경우에는 내부 범위 내에서 개인 예외를 발생 됩니다는 확신 하는 경우이 규칙에서 메시지를 표시 합니다.

## <a name="example"></a>예제
 이 규칙은 첫 번째 예제에서는 메서드 FirstCustomException 예외 클래스 예외에서 직접 파생 되 고 내부 때문에 됩니다. 규칙은 클래스를 공용 선언 하지만 클래스도 예외에서 직접 파생 SecondCustomException 클래스에서 발생 하지 않습니다. 세 번째 클래스도 발생 하지 않습니다 규칙에서 직접 파생 되지 않는 <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, 또는 <xref:System.ApplicationException?displayProperty=fullName>합니다.

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
