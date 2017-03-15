---
title: "CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다. | Microsoft Docs"
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
  - "FlagsEnumsShouldHavePluralNames"
  - "CA1714"
helpviewer_keywords: 
  - "CA1714"
  - "FlagsEnumsShouldHavePluralNames"
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|FlagsEnumsShouldHavePluralNames|  
|CheckId|CA1714|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 public 열거형에 <xref:System.FlagsAttribute?displayProperty=fullName>가 있고 이름이 's'로 끝나지 않았습니다.  
  
## 규칙 설명  
 <xref:System.FlagsAttribute> 특성은 둘 이상의 값을 지정할 수 있음을 나타내므로 이 특성으로 표시된 형식은 복수형 이름을 갖습니다.  예를 들어 요일을 정의하는 열거를 여러 날짜를 지정할 수 있는 응용 프로그램에서 사용하려는 경우  이 열거에는 <xref:System.FlagsAttribute>가 있어야 하며 'Days'라는 이름을 지정할 수 있습니다.  이와 비슷하지만 하루만 지정할 수 있는 열거는 이 특성을 포함할 수 없으며 'Day'라는 이름을 지정할 수 있습니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 열거 이름을 복수형 단어로 만들거나, 여러 열거 값을 동시에 지정할 수 없는 경우에는 <xref:System.FlagsAttribute> 특성을 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이름이 복수 단어이지만 's'로 끝나지 않는 경우에는 경고를 표시하지 않아도 안전합니다.  예를 들어 앞서 설명한 여러 날짜를 지정하는 열거의 이름이 'DaysOfTheWeek'이었다면 이 이름은 규칙의 논리를 위반하지만 의도된 것이 아닙니다.  이러한 위반은 표시하지 않아야 합니다.  
  
## 관련 규칙  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## 참고 항목  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [열거형 디자인](../Topic/Enum%20Design.md)