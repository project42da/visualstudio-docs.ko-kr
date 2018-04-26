---
title: 'CA2213: 삭제 가능한 필드는 삭제해야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be4efbd197a8146789b9646f6b5c467cc42815b1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: 삭제 가능한 필드는 삭제해야 합니다.
|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 구현 하는 형식은 <xref:System.IDisposable?displayProperty=fullName> 필드를 구현 하는 형식 선언 <xref:System.IDisposable>합니다. <xref:System.IDisposable.Dispose%2A> 필드의 메서드에 의해 호출 되지 않습니다는 <xref:System.IDisposable.Dispose%2A> 메서드 선언 형식입니다.

## <a name="rule-description"></a>규칙 설명
 형식이 삭제 된 모든 관리 되지 않는 리소스의;에 대 한 책임 구현 하 여 이렇게 <xref:System.IDisposable>합니다. 이 규칙에서는 삭제 가능한 형식 되는지 여부를 확인할 `T` 필드를 선언 `F` 삭제 가능한 형식 인스턴스의 즉 `FT`합니다. 각 필드에 대 한 `F`, 규칙에 대 한 호출을 찾으려고 시도 `FT.Dispose`합니다. 호출 하는 메서드를 검색 하는 규칙 `T.Dispose`와 단일 수준 낮은 (호출한 메서드에 의해 호출 된 메서드 `FT.Dispose`).

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 호출 <xref:System.IDisposable.Dispose%2A> 구현 하는 형식의 필드에서 <xref:System.IDisposable> 할당에 대 한 책임이 있으며, 필드에서 보유 하는 관리 되지 않는 리소스를 해제 하는 경우.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 자신이 담당 하지 않는 필드를 보유 하는 리소스를 해제에 대 한 또는 경우에이 규칙에서 경고를 표시를 안전 하 게 호출 <xref:System.IDisposable.Dispose%2A> 규칙 검사 보다 깊은 호출 수준에서 발생 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 `TypeA` 를 구현 하는 <xref:System.IDisposable> (`FT` 이전 설명의).

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

## <a name="example"></a>예제
 다음 예제에서는 형식 `TypeB` 필드를 선언 하 여이 규칙을 위반 하는 `aFieldOfADisposableType` (`F` 이전 설명의) 삭제 가능한 형식으로 (`TypeA`) 호출 하지 <xref:System.IDisposable.Dispose%2A> 필드입니다. `TypeB` 에 해당 `T` 이전 설명의 합니다.

 [!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>참고 항목
 <xref:System.IDisposable?displayProperty=fullName> [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)