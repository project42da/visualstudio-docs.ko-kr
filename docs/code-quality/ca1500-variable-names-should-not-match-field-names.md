---
title: 'CA1500: 변수 이름은 필드 이름과 달라야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa5c015205b5e325cfba06bb433c44ecc0631d5b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: 변수 이름은 필드 이름과 달라야 합니다.
|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|범주|Microsoft.Maintainability|
|변경 수준|필드 이름이 같은 매개 변수에서 발생 합니다.<br /><br /> --아님-필드와 메서드 매개 변수를 선언 하는 사용자가 변경한에 관계 없이 어셈블리 외부 볼 수 없는 경우.<br />분리-필드의 이름을 변경 하 고 어셈블리 외부에서 볼 수 있습니다.<br />-분석-매개 변수의 이름을 변경 하 고 이벤트를 선언 하는 메서드는 어셈블리 외부에서 볼 수 있습니다.<br /><br /> 필드와 이름이 같은 지역 변수에 발생:<br /><br /> --아님-사용자가 변경한에 관계 없이 어셈블리 외부의 필드를 볼 수 없는 경우.<br />--아님-경우 지역 변수의 이름을 변경 하 고 필드의 이름을 변경 하지 마십시오.<br />-분석-필드의 이름을 변경 하 고 어셈블리 외부에서 볼 수 있습니다.|

## <a name="cause"></a>원인
 인스턴스 메서드는 매개 변수 또는 이름이 선언 형식의 인스턴스 필드와 지역 변수를 선언 합니다. 규칙을 위반 하는 지역 변수를 catch 하려면 테스트 되는 어셈블리 디버깅 정보를 사용 하 여 작성 해야 하 고 관련된 프로그램 데이터베이스 (.pdb) 파일을 사용할 수 있어야 합니다.

## <a name="rule-description"></a>규칙 설명
 인스턴스 필드의 이름을 매개 변수나 지역 변수 이름과 경우 인스턴스 필드를 사용 하 여 액세스는 `this` (`Me` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 메서드 본문 내 키워드입니다. 코드를 유지 관리할 때 매개 변수/지역 변수를 선언 인스턴스 필드를 참조 하 가정 하는 이러한 차이 잊어버렸을 쉽습니다. 메서드 본문이 긴에 특히 유용합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 매개 변수/변수 또는 필드의 이름을 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 두 개의 규칙을 위반 경우를 보여 줍니다.

 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]