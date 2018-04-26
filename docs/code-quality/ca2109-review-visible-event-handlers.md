---
title: 'CA2109: 표시되는 이벤트 처리기를 검토하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2109
- ReviewVisibleEventHandlers
helpviewer_keywords:
- ReviewVisibleEventHandlers
- CA2109
ms.assetid: 8f8fa0ee-e94e-400e-b516-24d8727725d7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 481f03cc9f1699a794c0f34159afd7faa6a50c3d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2109-review-visible-event-handlers"></a>CA2109: 표시되는 이벤트 처리기를 검토하십시오.
|||
|-|-|
|TypeName|ReviewVisibleEventHandlers|
|CheckId|CA2109|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 public 또는 protected 이벤트 처리 메서드를 발견했습니다.

## <a name="rule-description"></a>규칙 설명
 외부에서 볼 수는 이벤트 처리 메서드를 검토 해야 하는 보안 문제를 표시 합니다.

 이벤트 처리 메서드는 반드시 필요한 경우를 제외하고 노출하면 안 됩니다. 이벤트 처리기를 노출 된 메서드를 호출 하는 대리자 형식으로 이벤트 및 처리기 서명이 일치 모든 이벤트에 추가할 수 있습니다. 이벤트는 코드에서 발생할 수 있습니다 및 신뢰할 수 있는 시스템 코드는 단추 클릭과 같은 사용자 작업에 대 한 응답에서으로 자주 발생 합니다. 이벤트 처리 메서드를 보안 검사를 추가 하지 않는 코드의 메서드를 호출 하는 이벤트 처리기를 등록 합니다.

 요청을 이벤트 처리기에 의해 호출 되는 메서드를 안정적으로 보호 수 없습니다. 도움말을 요구 하는 보안 코드를 신뢰할 수 없는 호출자 로부터 호출 스택의 호출자를 검사 하 여 보호 합니다. 이벤트 처리기 메서드가 실행 하는 경우 이벤트에 대 한 이벤트 처리기를 추가 하는 코드를 반드시 호출 스택에 나타나지 않습니다. 따라서 호출 스택을 수만 높은 신뢰할 수 있는 호출자에 게 이벤트 처리기 메서드를 호출 하면 합니다. 이렇게 하면 요청이 성공 하는 이벤트 처리기 메서드에 의해 수행 됩니다. 또한 메서드가 호출 될 때 요청 된 사용 권한 어설션 될 수도 있습니다. 이 규칙 위반 문제를 해결 하지의 위험 이러한 이유로, 이벤트 처리 메서드를 검토 한 후 평가할 수만 있습니다. 코드를 검토할 때는 다음 문제를 고려 합니다.

-   이벤트 처리기 위험 하거나 권한 어설션 또는 비관리 코드 권한 숨기기 등 악용 될 가능성이 있는 작업을 수행 합니까?

-   신뢰할 수 있는 호출자 스택에 서 언제 든 지만 항상 실행할 수 있기 때문 이란 하 고 사용자 코드에서 보안 위협 하는 중?

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 방법을 검토 하 고 다음 평가 합니다.

-   확인할 수 있는 사용자 이벤트 처리 메서드에서 public이 아닌?

-   이벤트 처리기에서 위험한 기능을 모두를 이동할 수 있습니까?

-   보안 요청을 적용 하는 경우이 방식으로 수행할 있습니다?

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 코드에 보안 위험이 없다고 되도록 신중 하 게 보안을 검토 한 후에이 규칙에서 경고를 표시 합니다.

## <a name="example"></a>예제
 다음 코드는 악성 코드가 악용할 수 하는 이벤트 처리 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]

## <a name="see-also"></a>참고 항목
 <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> <xref:System.EventArgs?displayProperty=fullName>
