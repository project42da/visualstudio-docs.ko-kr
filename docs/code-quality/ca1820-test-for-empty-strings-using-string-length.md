---
title: 'CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68e644a4e880f5468ec657f19efbf1a4f2d0c3d7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오.
|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 빈 문자열을 사용 하 여 비교 <xref:System.Object.Equals%2A?displayProperty=fullName>합니다.

## <a name="rule-description"></a>규칙 설명
 사용 하는 문자열 비교는 <xref:System.String.Length%2A?displayProperty=fullName> 속성 또는 <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> 메서드를 사용 하 여 보다 훨씬 빠릅니다 <xref:System.Object.Equals%2A>합니다. 때문에 이것이 <xref:System.Object.Equals%2A> 보다 훨씬 더 많은 MSIL 명령을 실행 <xref:System.String.IsNullOrEmpty%2A> 또는 검색 하는 명령 수가 <xref:System.String.Length%2A> 속성 값 및 0으로 비교 합니다.

 알고 있어야 하는 <xref:System.Object.Equals%2A> 및 <xref:System.String.Length%2A> = = 0 null 문자열에 다르게 동작 합니다. 값을 가져오려고 시도 하는 경우는 <xref:System.String.Length%2A> null 문자열에서 속성을 공용 언어 런타임에서 throw 된 <xref:System.NullReferenceException?displayProperty=fullName>합니다. 공용 언어 런타임; 예외를 throw 하지 않는 null 문자열 및 빈 문자열이 간의 비교를 수행 하는 경우 비교 반환 `false`합니다. Null에 대 한 테스트 이러한 두 방법의 상대 성능을 현저 하 게 적용 되지 않습니다. 대상으로 할 때 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]를 사용 하 여는 <xref:System.String.IsNullOrEmpty%2A> 메서드. 그렇지 않은 경우 사용 하 여는 <xref:System.String.Length%2A> = = 가능 하면 비교 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반을 해결 하려면 변경 사용할 비교는 <xref:System.String.Length%2A> 속성과 null 문자열에 대 한 테스트 합니다. 대상으로 하는 경우 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]를 사용 하 여는 <xref:System.String.IsNullOrEmpty%2A> 메서드.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 성능이 중요 하지 않은 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 빈 문자열에 대 한 확인 하는 데 사용 되는 다양 한 기술을 보여 줍니다.

 [!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]