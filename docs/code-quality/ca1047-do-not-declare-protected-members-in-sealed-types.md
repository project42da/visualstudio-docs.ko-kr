---
title: 'CA1047: protected 멤버를 sealed 형식으로 선언하지 마십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f25af4cf9ddd86bd28b5909242ab55f35a467438
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: protected 멤버를 sealed 형식으로 선언하지 마십시오.
|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 공용 형식이 `sealed` (`NotInheritable` Visual basic에서) 하 고 보호 된 멤버 또는 보호 된 중첩된 형식을 선언 합니다. 이 규칙에 대 한 위반을 보고 하지 않습니다 <xref:System.Object.Finalize%2A> 이 패턴을 따라야 하는 방법입니다.

## <a name="rule-description"></a>규칙 설명
 형식에서는 상속하는 형식에서 멤버에 액세스하거나 멤버를 재정의할 수 있도록 하기 위해 protected 멤버를 선언합니다. 기본적으로 sealed 형식에 대 한 메서드를 보호 하는 호출할 수 없습니다 봉인 된 형식에서 상속할 수는 없습니다.

 C# 컴파일러는이 오류에 대 한 경고를 실행합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면를 private 멤버의 액세스 수준을 변경 하거나 형식을 상속할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 상태로 유지 형식을 현재 상태에서 유지 관리 문제가 발생할 수 있습니다 하 고는 이점을 제공 하지 않습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]