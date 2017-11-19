---
title: "CA1023: 인덱서 되어서는 안 다차원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c3b677f4cde4a38b2e682e36090e7a86f68e4fc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: 다차원 인덱서는 사용하지 마십시오.
|||  
|-|-|  
|TypeName|IndexersShouldNotBeMultidimensional|  
|CheckId|CA1023|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 형식이 둘 이상의 인덱스를 사용 하는 public 또는 protected 인덱서를 포함 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 인덱서, 즉, 인덱싱된 속성에는 단일 인덱스를 사용 해야 합니다. 다차원 인덱서는 라이브러리의 유용성이 줄어들 수 있습니다. 디자인에 인덱스를 여러 개 필요한 경우 해당 형식이 논리 데이터 저장소를 나타내는지를 다시 고려할 합니다. 파일이 없으면 메서드를 사용 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 유일한 정수나 문자열 인덱스를 사용 하도록 디자인을 변경 하거나 인덱서 대신 메서드를 사용 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 형식 `DayOfWeek03`, 규칙을 위반 하는 다차원 인덱서를 사용 합니다. 인덱서 변환 형식으로 볼 수 있습니다 및 메서드로 노출 보다 적절 하 게 됩니다. 형식으로 다시 디자인 `RedesignedDayOfWeek03` 규칙을 만족 하 합니다.  
  
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)  
  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)