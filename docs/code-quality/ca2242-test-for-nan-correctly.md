---
title: "CA2242: NaN에 대해 정확하게 테스트하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TestForNaNCorrectly"
  - "CA2242"
helpviewer_keywords: 
  - "CA2242"
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 11
---
# CA2242: NaN에 대해 정확하게 테스트하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TestForNaNCorrectly|  
|CheckId|CA2242|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 식이 <xref:System.Single.Nan?displayProperty=fullName> 또는 <xref:System.Double.Nan?displayProperty=fullName>에 대한 값을 테스트합니다.  
  
## 규칙 설명  
 산술 연산이 정의되지 않은 경우 숫자가 아닌 값을 나타내는 <xref:System.Double.NaN?displayProperty=fullName>이 나타납니다.  값과 <xref:System.Double.NaN?displayProperty=fullName>이 같은지 테스트하는 식은 항상 `false`를 반환합니다.  값과 <xref:System.Double.NaN?displayProperty=fullName>이 다른지 테스트하는 식은 항상 `true`를 반환합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하고 값이 <xref:System.Double.NaN?displayProperty=fullName>을 나타내는지 정확히 확인하려면 <xref:System.Single.IsNan%2A?displayProperty=fullName> 또는 <xref:System.Double.IsNan%2A?displayProperty=fullName>을 사용하여 값을 테스트합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Double.NaN?displayProperty=fullName>에 대한 값을 잘못 테스트하는 식과 <xref:System.Double.IsNaN%2A?displayProperty=fullName>을 올바로 사용하여 값을 테스트하는 두 개의 식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-cs[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]