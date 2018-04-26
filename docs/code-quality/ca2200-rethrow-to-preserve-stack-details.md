---
title: 'CA2200: 스택 정보를 유지하도록 다시 throw하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 688c10802b144c619b22b06309cec6dee5efc52e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: 스택 정보를 유지하도록 다시 throw하십시오.
|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 예외가 다시 throw 됩니다. 및 예외에 명시적으로 지정 되는 `throw` 문.

## <a name="rule-description"></a>규칙 설명
 예외가 throw 되 면 수행 되는 정보의 일부로 스택 추적입니다. 스택 추적은 목록에 예외를 throw 하는 예외를 catch 하는 방법으로 끝나는 방법으로 시작 하는 메서드 호출 계층 구조입니다. 예외를 지정 하 여 예외가 예외가 다시 throw 하는 경우는 `throw` 문, 스택 추적 현재 메서드에서 다시 시작 되 고 예외를 발생 시킨 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실 됩니다. 예외와 원래 스택 추적 정보, 사용 된 `throw` 예외를 지정 하지 않고 문입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 예외를 명시적으로 지정 하지 않고 예외 다시 throw 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 메서드를 `CatchAndRethrowExplicitly`, 규칙을 위반 하는 메서드는 `CatchAndRethrowImplicitly`, 규칙을 만족 하는 합니다.

 [!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
 [!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]