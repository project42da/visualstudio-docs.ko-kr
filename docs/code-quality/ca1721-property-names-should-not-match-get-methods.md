---
title: 'CA1721: 속성 이름은 Get 메서드와 달라야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c1b6502647644b59291b9d27ccf633d089d7110
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: 속성 이름은 Get 메서드와 달라야 합니다.
|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 멤버의 이름을 'Get'로 시작 되며 그렇지 않으면 일치 하는 공용 또는 보호 된 속성의 이름. 예를 들어 ' 메서드와 ' 라는 'Color' 속성 라고 하는 메서드가 포함 된 형식은이 규칙을 위반 합니다.

## <a name="rule-description"></a>규칙 설명
 Get 메서드 및 속성 서로 분명히 구분 하는 이름을 사용 해야 합니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리를 익히는 데 필요한 라이브러리를 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 개발 하는 신뢰성이 향상 하는 시간과 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이름을 변경 하는 'Get'이 접두사로 메서드의 이름을 일치 하지 않습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

> [!NOTE]
>  Get 메서드가 IExtenderProvider 인터페이스를 구현 하 여 발생 하는 경우이 경고를 제외할 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 속성과 메서드를 포함 합니다.

 [!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)