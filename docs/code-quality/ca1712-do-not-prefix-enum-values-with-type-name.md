---
title: "CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1712"
  - "DoNotPrefixEnumValuesWithTypeName"
helpviewer_keywords: 
  - "CA1712"
  - "DoNotPrefixEnumValuesWithTypeName"
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotPrefixEnumValuesWithTypeName|  
|CheckId|CA1712|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 열거형에 이름이 열거형의 형식 이름으로 시작하는 멤버가 들어 있습니다.  
  
## 규칙 설명  
 형식 정보는 개발 도구에서 제공하므로 열거형 멤버의 이름에 형식 이름을 접두사로 사용하지 않습니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이를 통해 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간이 단축되고, 관리 코드 개발에 대한 전문 지식을 갖춘 작업자가 라이브러리를 개발했다는 신뢰성이 향상됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 열거형 멤버에서 형식 이름 접두사를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이름이 잘못 지정된 열거형과 올바로 지정된 열거형을 보여 줍니다.  
  
 [!code-cs[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CSharp/ca1712-do-not-prefix-enum-values-with-type-name_1.cs)]
 [!code-cpp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CPP/ca1712-do-not-prefix-enum-values-with-type-name_1.cpp)]
 [!code-vb[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/VisualBasic/ca1712-do-not-prefix-enum-values-with-type-name_1.vb)]  
  
## 관련 규칙  
 [CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## 참고 항목  
 <xref:System.Enum?displayProperty=fullName>