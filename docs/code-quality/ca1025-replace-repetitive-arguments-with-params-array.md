---
title: 'CA1025: 반복 인수를 매개 변수 배열로 바꾸십시오. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9d42e7109d75f14d51e0e7834bc996f6f8864dc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: 반복 인수를 매개 변수 배열로 바꾸십시오.
|||  
|-|-|  
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|  
|CheckId|CA1025|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 공용 형식에서 public 또는 protected 메서드가 세 개 이상의 매개 변수를 가지 며 해당 마지막 세 매개 변수는 동일한 형식  
  
## <a name="rule-description"></a>규칙 설명  
 반복 되는 인수 대신 매개 변수 배열을 사용 하 여 인수의 정확한 개수 알 수 없는 하 고 가변 인수가 같은 형식 이거나 같은 형식으로 전달할 수 있습니다. 예를 들어는 <xref:System.Console.WriteLine%2A> 개수에 관계 없이 허용 하도록 매개 변수 배열을 사용 하는 범용 오버 로드를 제공 하는 메서드 <xref:System.Object> 인수입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 매개 변수 배열을 사용 하 여 반복 되는 인수를 바꿉니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙;에서 경고를 표시 하지 않아도 안전는 항상 그러나이 디자인 유용성 문제를 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.  
  
 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]