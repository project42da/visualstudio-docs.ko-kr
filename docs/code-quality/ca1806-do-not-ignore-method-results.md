---
title: 'CA1806: 메서드 결과를 무시하지 마십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 6b0d5870b29fea9d6ef99a3951ef12d938b0eab3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: 메서드 결과를 무시하지 마십시오.
|||
|-|-|
|TypeName|DoNotIgnoreMethodResults|
|CheckId|CA1806|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 이 경고에 대 한 여러 가지가 있습니다.

-   새 개체가 만들어지지만 사용 되지 않습니다.

-   만들고 새 문자열을 반환 하는 메서드가 호출 되 고 새 문자열이 사용 되지 합니다.

-   오류 코드나 HRESULT를 반환 하는 COM 또는 P/Invoke 메서드가 사용 되지 않습니다. 규칙 설명

 불필요 한 개체 생성 및 사용 하지 않는 개체의 연결 된 가비지 수집에는 성능이 저하 됩니다.

 문자열은 변경 하 고 String.ToUpper 등 메서드 호출에서 문자열의 인스턴스를 수정 하는 대신 문자열의 새 인스턴스를 반환 합니다.

 오류 코드나 HRESULT를 무시 합니다. 리소스가 부족 또는 오류 상태에 예기치 않은 동작이 발생할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 메서드는 사용 되지 않는 B 개체의 새 인스턴스를 만드는 경우 인스턴스를 다른 메서드에 인수로 전달 하거나 인스턴스를 변수에 할당 합니다. 개체 만들기 필요가 없는 경우 제거 된 하십시오-또는-

 메서드 A B 메서드를 호출 하지만 B 메서드가 반환 하는 새 문자열 인스턴스를 사용 하지 않는 경우. 인스턴스를 다른 메서드에 인수로 전달, 인스턴스를 변수에 할당 합니다. 또는 필요 없는 경우 호출을 제거 합니다.

 -또는-

 또는 오류 코드를 메서드 A B 메서드를 호출 하지만 HRESULT를 사용 하지 않는 경우이 메서드는 반환 합니다. 조건문에서 결과 사용 하 고 결과 변수에 할당 또는를 다른 메서드에 인수로 전달 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 개체를 만드는 몇 가지 용도로 사용 하지 않는 한이 규칙에서는 경고를에서 표시 하지 마십시오.

## <a name="example"></a>예제
 다음 예제에서는 호출 String.Trim의 결과 무시 하는 클래스를 보여 줍니다.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]

## <a name="example"></a>예제
 다음 예제에서 호출 된 변수를 다시 String.Trim의 결과 할당 하 여 위반을 해결 합니다.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]

## <a name="example"></a>예제
 다음 예제에서는 생성 된 개체를 사용 하지 않는 메서드를 보여 줍니다.

> [!NOTE]
>  Visual Basic에서는이 위반을 재현할 수 없는 합니다.

 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]

## <a name="example"></a>예제
 다음 예제에서는 불필요 한 개체 생성을 제거 하 여 위반을 해결 합니다.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)]

<!-- Examples don't exist for the below... -->
<!--
## Example
 The following example shows a method that ignores the error code that the native method GetShortPathName returns.

## Example
 The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.
-->