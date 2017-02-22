---
title: "CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오. | Microsoft Docs"
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
  - "DoNotMarkEnumsWithFlags"
  - "CA2217"
helpviewer_keywords: 
  - "CA2217"
  - "DoNotMarkEnumsWithFlags"
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotMarkEnumsWithFlags|  
|CheckId|CA2217|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 외부에서 볼 수 있는 열거형이 <xref:System.FlagsAttribute>로 표시되어 있고, 2의 거듭제곱 또는 열거형에 정의된 다른 값의 조합이 아닌 값이 하나 이상 들어 있습니다.  
  
## 규칙 설명  
 열거형에는 열거형에 정의된 각 값이 2의 거듭제곱이거나 정의된 값의 조합인 경우에만 <xref:System.FlagsAttribute>가 존재할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 열거형에서 <xref:System.FlagsAttribute>를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 값 3이 들어 있는 Color라는 열거형을 보여 줍니다. 이 값은 2의 거듭제곱이 아니며 정의되어 있는 값의 조합이 아닙니다.  따라서 Color 열거형은 <xref:System.FlagsAttribute>로 표시하지 말아야 합니다.  
  
 [!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
 [!code-cs[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]  
  
## 예제  
 다음 예제에서는 System.FlagsAttribute로 표시하기 위한 요구 사항에 맞는 Days라는 열거형을 보여 줍니다.  
  
 [!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
 [!code-cs[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]  
  
## 관련 규칙  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## 참고 항목  
 <xref:System.FlagsAttribute?displayProperty=fullName>