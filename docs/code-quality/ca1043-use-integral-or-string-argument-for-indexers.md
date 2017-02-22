---
title: "CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오. | Microsoft Docs"
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
  - "CA1043"
  - "UseIntegralOrStringArgumentForIndexers"
helpviewer_keywords: 
  - "CA1043"
  - "UseIntegralOrStringArgumentForIndexers"
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseIntegralOrStringArgumentForIndexers|  
|CheckId|CA1043|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식에 <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName> 또는 <xref:System.String?displayProperty=fullName> 이외의 인덱스 형식을 사용하는 public 또는 protected 인덱서가 들어 있습니다.  
  
## 규칙 설명  
 인덱서, 즉 인덱싱된 속성은 인덱스에 정수 또는 문자열 형식을 사용해야 합니다.  이러한 형식은 대개 데이터 구조를 인덱싱하는 데 사용되며 라이브러리의 유용성을 증가시킵니다.  디자인 타임에 특정 정수 또는 문자열 형식을 지정할 수 없는 경우에는 <xref:System.Object> 형식의 사용을 제한해야 합니다.  디자인에 다른 형식의 인덱스가 필요하면 해당 형식이 논리 데이터 저장소를 나타내는지를 다시 고려해 보아야 합니다.  논리 데이터 저장소를 나타내지 않으면 메서드를 사용합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 인덱스를 정수 또는 문자열 형식으로 변경하거나 인덱서 대신 메서드를 사용합니다.  
  
## 경고를 표시하지 않는 경우  
 비표준 인덱서의 필요성을 신중하게 고려한 후에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Int32> 인덱스를 사용하는 인덱서를 보여 줍니다.  
  
 [!CODE [FxCop.Design.IntegralOrStringIndexers#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers#1)]  
  
## 관련 규칙  
 [CA1023: 다차원 인덱서는 사용하지 마십시오.](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)  
  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)