---
title: 'CA2101: P Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc32aedf38430ab3ce9657f3a7e4d8d9e416fa57
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.
|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 플랫폼 호출 문자열 매개 변수 멤버 부분적으로 신뢰할 수 있는 호출자 허용 하며 문자열을 명시적으로 마샬링하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 유니코드에서 ANSI로 변환 하는 경우 있기 특정 ANSI 코드 페이지에 모든 유니코드 문자를 나타낼 수 있습니다. *최적된 매핑을* 표현할 수 없는 문자에 대 한 문자를 대체 하 여이 문제를 해결 하려고 합니다. 이 기능을 사용 하면 선택 되는 문자를 제어할 수 없으므로 잠재적 보안 취약점을 발생할 수 있습니다. 예를 들어 악성 코드가 의도적으로 일으킬 같은 파일 시스템에 대 한 특수 문자를 변환 하는 특정 코드 페이지에서 찾을 수 없는 문자를 포함 하는 유니코드 문자열 '..' 또는 '/'입니다. Note 또한 문자열을 ANSI로 변환 되기 전에 특수 문자에 대 한 보안 검사가 자주 수행 되도록 합니다.

 최적된 매핑을 공간 (mb) WChar 관리 되지 않는 변환의 경우 기본값입니다. 최적된 매핑을, 명시적으로 해제 하지 않은 코드가이 문제로 인해는 보안상 취약 한 부분이 있을 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 명시적으로 문자열 데이터 형식을 맞게 마샬링하십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하 고 문제를 위반을 해결 하는 방법을 보여 주는 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]