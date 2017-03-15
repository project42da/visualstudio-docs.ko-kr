---
title: "CA1819: 속성은 배열을 반환해서는 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PropertiesShouldNotReturnArrays"
  - "CA1819"
helpviewer_keywords: 
  - "PropertiesShouldNotReturnArrays"
  - "CA1819"
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 22
---
# CA1819: 속성은 배열을 반환해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PropertiesShouldNotReturnArrays|  
|CheckId|CA1819|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경|  
  
## 원인  
 public 형식의 public 또는 protected 속성이 배열을 반환합니다.  
  
## 규칙 설명  
 속성에서 반환된 배열은 속성이 읽기 전용이더라도 쓰기 금지되지 않습니다.  배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다.  일반적으로 사용자는 이러한 속성을 호출할 경우 성능에 부정적인 영향을 준다는 것을 인식하지 못합니다.  특히 속성을 인덱싱된 속성으로 사용하면 성능이 더 나빠집니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 속성을 메서드로 만들거나 속성에서 컬렉션을 반환하도록 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 특성은 배열을 반환하는 속성을 포함할 수 있지만 컬렉션을 반환하는 속성은 포함할 수 없습니다.  [System.Attribute](assetId:///System.Attribute?qualifyHint=False&autoUpgrade=True) 클래스로부터 파생된 특성의 속성에 대해 발생한 경고를 표시하지 않을 수 있습니다.  그렇지 않으면 이 규칙에서는 경고를 표시해야 합니다.  
  
## 규칙 위반 예  
  
### 설명  
 다음 예제에서는 이 규칙을 위반하는 속성을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]  
  
### 설명  
 이 규칙 위반 문제를 해결하려면 속성을 메서드로 만들거나 속성에서 배열 대신 컬렉션을 반환하도록 변경합니다.  
  
## 속성을 메서드로 변경하는 예제  
  
### 설명  
 다음 예제에서는 속성을 메서드로 변경하여 위반 문제를 해결합니다.  
  
### 코드  
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-cs[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]  
  
## 컬렉션 반환 예제  
  
### 설명  
 다음 예제에서는 속성에서 컬렉션을 반환하도록 변경하여 위반 문제를 해결합니다.  
  
 <xref:System.Collection.ObjectModel.ReadOnlyCollection?displayProperty=fullName>.  
  
### 코드  
 [!code-cs[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]  
  
## 사용자가 속성을 수정할 수 있도록 허용  
  
### 설명  
 클래스 소비자가 속성을 수정할 수 있도록 허용할 수 있습니다.  다음 예제에서는 이 규칙을 위반하는 읽기\/쓰기 속성을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]  
  
### 설명  
 다음 예제에서는 속성에서 <xref:System.Collection.ObjectModel.Collection?displayProperty=fullName>을 반환하도록 변경하여 위반 문제를 해결합니다.  
  
### 코드  
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-cs[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]  
  
## 관련 규칙  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)