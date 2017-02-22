---
title: "CA1023: 다차원 인덱서는 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IndexersShouldNotBeMultidimensional"
  - "CA1023"
helpviewer_keywords: 
  - "CA1023"
  - "IndexersShouldNotBeMultidimensional"
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1023: 다차원 인덱서는 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IndexersShouldNotBeMultidimensional|  
|CheckId|CA1023|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식에 둘 이상의 인덱스를 사용하는 public 또는 protected 인덱서가 들어 있습니다.  
  
## 규칙 설명  
 인덱서, 즉 인덱싱된 속성은 단일 인덱스를 사용해야 합니다.  다차원 인덱서를 사용하면 라이브러리의 유용성이 현저히 줄어들 수 있습니다.  디자인에 여러 인덱스가 필요하면 해당 형식이 논리 데이터 저장소를 나타내는지를 다시 고려해 보아야 합니다.  그렇지 않을 경우에는 메서드를 사용합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 정수\(long\) 또는 문자열 인덱스를 사용하도록 디자인을 변경하거나 인덱서 대신 메서드를 사용합니다.  
  
## 경고를 표시하지 않는 경우  
 비표준 인덱서의 필요성을 신중하게 고려한 후에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 다차원 인덱서가 있는 `DayOfWeek03` 형식을 보여 줍니다.  인덱서가 변환 형식으로 보일 수 있으므로 메서드로 노출하는 것이 더 적합합니다.  규칙을 만족하기 위해 형식을 `RedesignedDayOfWeek03`으로 다시 디자인합니다.  
  
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-cs[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]  
  
## 관련 규칙  
 [CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)  
  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)