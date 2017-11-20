---
title: "CA1043: 인덱서에 정수 또는 문자열 인수를 사용 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aeaaf07dd3590e4dd703cfa239c48cb7e86b7f43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.
|||  
|-|-|  
|TypeName|UseIntegralOrStringArgumentForIndexers|  
|CheckId|CA1043|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 형식이 포함 이외의 인덱스 유형을 사용 하는 public 또는 protected 인덱서가 <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, 또는 <xref:System.String?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 인덱서, 즉, 인덱싱된 속성에는 인덱스에 대 한 정수 또는 문자열 형식을 사용 해야 합니다. 이러한 형식은 일반적으로 데이터 구조를 인덱싱하는 데 사용 됩니다 하 고 라이브러리의 유용성을 증가 시킵니다. 사용은 <xref:System.Object> 형식 특정 정수 또는 문자열 형식 디자인 타임에 지정할 수 없는 이러한 경우로만 제한 해야 합니다. 인덱스에 대 한 다른 형식이 필요한 형식을 디자인, 유형을 논리 데이터 저장소를 나타내는지 여부를 다시 고려해 보아야 합니다. 논리 데이터 저장소를 나타내지 않는 경우 메서드를 사용 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 정수 또는 문자열 형식으로 인덱스를 변경 하거나 인덱서 대신 메서드를 사용 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 인덱서를 사용 하는 <xref:System.Int32> 인덱스입니다.  
  
 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1023: 다차원 인덱서는 사용하지 마십시오.](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)  
  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)