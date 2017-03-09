---
title: "CA1813: 봉인되지 않은 특성을 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1813"
  - "AvoidUnsealedAttributes"
helpviewer_keywords: 
  - "AvoidUnsealedAttributes"
  - "CA1813"
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1813: 봉인되지 않은 특성을 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidUnsealedAttributes|  
|CheckId|CA1813|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.Attribute?displayProperty=fullName>에서 상속 받은 public 형식이 abstract도 아니고 sealed\(Visual Basic에서는 `NotInheritable`\)도 아닙니다.  
  
## 규칙 설명  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리는 사용자 지정 특성을 검색하는 메서드를 제공합니다.  기본적으로 이러한 메서드는 특성 상속 계층 구조를 검색합니다. 예를 들어, <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>는 지정된 특성 형식 또는 지정된 특성 형식을 확장하는 모든 특성 형식을 검색합니다.  특성을 봉인하면 상속 계층 구조를 검색하지 않으므로 성능이 향상될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 특성 형식을 봉인하거나 abstract로 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  특성 계층 구조를 정의하면서 특성을 봉인하거나 abstract로 만들 수 없을 경우에만 경고를 제외해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 만족하는 사용자 지정 특성을 보여 줍니다.  
  
 [!code-cs[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]  
  
## 관련 규칙  
 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)  
  
## 참고 항목  
 [특성](../Topic/Attributes1.md)