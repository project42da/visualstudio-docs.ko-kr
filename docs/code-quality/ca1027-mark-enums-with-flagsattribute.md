---
title: "CA1027: 열거형을 FlagsAttribute로 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MarkEnumsWithFlags"
  - "CA1027"
helpviewer_keywords: 
  - "CA1027"
  - "MarkEnumsWithFlags"
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1027: 열거형을 FlagsAttribute로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkEnumsWithFlags|  
|CheckId|CA1027|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 열거형의 값이 2의 거듭제곱이거나 열거형에 정의된 다른 값의 조합이며 <xref:System.FlagsAttribute?displayProperty=fullName> 특성이 없습니다.  가양성\(false positives\)을 줄이기 위해 이 규칙에서는 값이 연속되는 열거형에 대해서는 위반을 보고하지 않습니다.  
  
## 규칙 설명  
 열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다.  명명된 상수를 의미 있게 조합할 수 있는 경우 열거형에 <xref:System.FlagsAttribute>를 적용합니다.  여기서는 리소스를 사용할 수 있는 요일을 추적하는 응용 프로그램에 사용되는 요일의 열거형을 예로 듭니다.  <xref:System.FlagsAttribute>가 있는 열거형을 사용하여 각 리소스의 사용 가능 여부를 인코딩하면 요일의 조합을 나타낼 수 있습니다.  이 특성이 없으면 요일을 하나만 나타낼 수 있습니다.  
  
 조합 가능한 열거형이 저장되는 필드의 경우 각 열거형 값은 필드에서 비트 그룹으로 처리됩니다.  따라서 이러한 필드를 *비트 필드*라고도 합니다.  비트 필드에 저장하기 위해 열거형 값을 조합하려면 Boolean 조건 연산자를 사용합니다.  비트 필드를 테스트하여 특정 열거형 값이 있는지 여부를 확인하려면 Boolean 논리 연산자를 사용합니다.  조합된 열거형 값을 비트 필드에 올바르게 저장하고 검색하려면 열거형에 정의된 각각의 값이 2의 거듭제곱이어야 합니다.  그렇지 않은 경우에는 Boolean 논리 연산자를 통해 필드에 저장된 개별 열거형 값을 추출할 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 열거형에 <xref:System.FlagsAttribute>를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 열거형 값의 조합을 허용하지 않으려면 이 규칙에서 경고를 표시하지 않습니다.  
  
## 예제  
 다음 예제에서 `DaysEnumNeedsFlags`는 <xref:System.FlagsAttribute> 사용 요건을 충족하지만 이 특성을 사용하지 않는 열거형입니다.  `ColorEnumShouldNotHaveFlag` 열거형은 2의 거듭제곱 값을 포함하지 않지만 <xref:System.FlagsAttribute>를 잘못 지정합니다.  따라서 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md) 규칙을 위반합니다.  
  
 [!code-cs[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]  
  
## 관련 규칙  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## 참고 항목  
 <xref:System.FlagsAttribute?displayProperty=fullName>