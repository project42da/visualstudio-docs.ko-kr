---
title: "CA1018: 특성을 AttributeUsageAttribute로 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1018"
  - "MarkAttributesWithAttributeUsage"
helpviewer_keywords: 
  - "CA1018"
  - "MarkAttributesWithAttributeUsage"
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkAttributesWithAttributeUsage|  
|CheckId|CA1018|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 사용자 지정 특성에 <xref:System.AttributeUsageAttribute?displayProperty=fullName> 특성이 없습니다.  
  
## 규칙 설명  
 사용자 지정 특성을 정의할 때는 <xref:System.AttributeUsageAttribute> 사용을 표시하여 사용자 지정 특성을 적용할 수 있는 소스 코드의 위치를 나타냅니다.  특성의 의미 및 용도에 따라 코드에서의 유효한 위치가 결정됩니다.  예를 들어, 유지 관리 및 라이브러리에서 각 형식 향상을 담당하고 있는 책임자를 식별하고 책임이 항상 형식 수준에서 할당되는 특성을 정의할 수 있습니다.  이 경우 컴파일러는 클래스, 열거형 및 인터페이스에서 특성을 활성화해야 하지만 메서드, 이벤트 또는 속성에서는 활성화해서는 안 됩니다.  특성이 어셈블리에 허용되는지 여부는 조직 정책 및 절차에 따라 결정됩니다.  
  
 <xref:System.AttributeTargets?displayProperty=fullName> 열거형은 사용자 지정 특성에 대해 지정할 수 있는 대상을 정의합니다.  <xref:System.AttributeUsageAttribute>를 생략하는 경우 <xref:System.AttributeTargets> 열거형의 `All`에 정의된 것처럼 사용자 지정 특성이 모든 대상에 대해 유효하게 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.AttributeUsageAttribute>를 사용하여 특성의 대상을 지정합니다.  다음 예제를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 메시지를 제외하는 대신 이 규칙 위반 문제를 해결해야 합니다.  특성이 <xref:System.AttributeUsageAttribute>를 상속하는 경우에도 코드 유지 관리를 단순화하기 위해 특성이 있어야 합니다.  
  
## 예제  
 다음 예제에서는 두 개의 특성을 정의합니다.  `BadCodeMaintainerAttribute`는 <xref:System.AttributeUsageAttribute> 문이 생략된 올바르지 않은 특성이고 `GoodCodeMaintainerAttribute`는 이 섹션 앞부분에서 설명한 특성을 올바르게 구현합니다.  `DeveloperName` 속성은 디자인 규칙 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)에 따라 필요하며 코드를 완성하기 위해 포함되었습니다.  
  
 [!code-cs[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]  
  
## 관련 규칙  
 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## 참고 항목  
 [특성](../Topic/Attributes1.md)