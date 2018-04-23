---
title: 'CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d46bc7bcfa8c1918091fabbbd759172259ea9ba6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.
|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 버전 1.0 및 1.1의는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], public 또는 protected 메서드에 포함 되어는 `try` / `catch` / `finally` 블록입니다. `finally` 블록이 보안 상태를 되돌리려면 나타나고 묶지 않았습니다는 `finally` 블록입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙을 찾습니다 `try` / `finally` 버전 1.0 및 1.1의 대상으로 하는 코드에서 차단 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 호출 스택에 있는 악의적인 예외 필터에 취약할 수 있는 합니다. 필터 전에 실행할 수 있습니다 가장과 같은 중요 한 작업 try 블록에서 발생 하는 경우 예외가 throw 되는 `finally` 블록입니다. 가장 예제에 대 한 필터 가장된 사용자로 실행 될을 의미 합니다. 필터는 Visual Basic에서 현재 구현할 수 있습니다.

> [!WARNING]
>  **참고** 버전 2.0 이상에 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 런타임에서 자동으로 보호는 `try` / `catch` /  `finally` 재설정 악의적인 예외 필터에서 차단 메서드 내에서 직접 예외 블록이 들어 있는입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 배치는 래핑되지 않은 `try` / `finally` 외부 try 블록에 있습니다. 뒤에 오는 두 번째 예제를 참조 하십시오. 이렇게 하면는 `finally` 필터 코드 보다 먼저 실행 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="pseudo-code-example"></a>의사 코드 예제

### <a name="description"></a>설명
 다음 의사 코드에서는 이 규칙에 의해 검색되는 패턴을 보여 줍니다.

### <a name="code"></a>코드

```
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

## <a name="example"></a>예제
 다음 의사 코드는 코드를 보호 하 고이 규칙을 만족 시키는 데 사용할 수 있는 패턴을 보여 줍니다.

```
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```