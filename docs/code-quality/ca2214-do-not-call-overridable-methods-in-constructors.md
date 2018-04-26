---
title: 'CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5ebcd4164f9db28d4cb1f150ee3a4bb21b21cde
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.
|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 봉인 되지 않은 형식의 생성자는 해당 클래스에 정의 된 가상 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명
 가상 메서드를 호출할 때 메서드를 실행 하는 실제 형식이 런타임이 될 때까지 선택 하지 않았습니다. 생성자는 가상 메서드를 호출할 때 있기 생성자 메서드를 호출 하는 인스턴스에 대해 실행 되지 않았습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 형식의 생성자 내에서 형식의 가상 메서드를 호출 하지 마십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 가상 메서드에 대 한 호출을 제거 하기 위해 생성자를 다시 디자인 해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반의 효과 보여 줍니다. 테스트 응용 프로그램의 인스턴스를 만들고 `DerivedType`, 기본 클래스에 이르게 (`BadlyConstructedType`) 생성자를 실행 합니다. `BadlyConstructedType`생성자는 가상 메서드의 제대로 호출 `DoSomething`합니다. 출력에서 볼 수 있듯이 `DerivedType.DoSomething()` 되기 전에 실행 되며 `DerivedType`의 생성자를 실행 합니다.

 [!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
 [!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

 이 예제의 결과는 다음과 같습니다.

 **기본 생성자를 호출 합니다. ** 
 **파생 DoSomething 라고-초기화? 더**
**호출 ctor 파생 합니다.**