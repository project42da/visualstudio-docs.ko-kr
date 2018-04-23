---
title: 'CA2139: 투명한 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f10eca96b9a55d6dfd8d5550bcf7b2d5c08a1a5b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: 투명한 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.
|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 투명 한 메서드가로 표시 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 특성입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 투명 한 프로세스를 사용 하 여 손상 예외를 처리 하려고 시도 하는 모든 메서드에 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 특성입니다. 프로세스 손상 예외는 이러한 예외의 CLR 버전 4.0 예외 분류 <xref:System.AccessViolationException>합니다. HandleProcessCorruptedStateExceptionsAttribute 특성은 보안에 중요한 메서드에서만 사용할 수 있으며 투명 메서드에 적용되는 경우 무시됩니다. 프로세스 손상 예외를 처리 하려면이 메서드는 보안에 중요 하거나 보안 안전에 중요 한가 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 제거의 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 특성을 사용 하 여 메서드를 표시 하거나는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예제에서는 투명 메서드가로 표시 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 특성 및 규칙에 실패 합니다. 메서드는으로 표시 해야는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.

 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]