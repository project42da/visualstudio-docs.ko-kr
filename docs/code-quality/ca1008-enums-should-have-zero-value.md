---
title: "CA1008: 열거형에는 0 값이 있어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1008"
  - "EnumsShouldHaveZeroValue"
helpviewer_keywords: 
  - "CA1008"
  - "EnumsShouldHaveZeroValue"
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 21
---
# CA1008: 열거형에는 0 값이 있어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|EnumsShouldHaveZeroValue|  
|CheckId|CA1008|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님 \- 플래그를 사용하지 않는 열거형에 **None** 값을 추가해야 하는 경우. 주요 변경 \- 열거형 값의 이름을 바꾸거나 열거형 값을 제거해야 하는 경우|  
  
## 원인  
 <xref:System.FlagsAttribute?displayProperty=fullName>가 적용되지 않은 열거형에서 0 값을 가진 멤버를 정의하지 않습니다. 또는 <xref:System.FlagsAttribute>가 적용된 열거형에서 0 값을 가진 멤버를 정의하지만 해당 이름이 'None'이 아니거나 열거형에서 0 값을 가진 여러 개의 멤버를 정의합니다.  
  
## 규칙 설명  
 초기화되지 않은 열거형의 기본값은 다른 값 형식과 마찬가지로 0입니다.  플래그 특성을 사용하지 않는 열거형에서는 기본값이 열거형의 유효한 값이 되도록 값이 0인 멤버를 정의해야 합니다.  적절한 경우 멤버의 이름을 'None'으로 지정합니다.  그렇지 않은 경우 가장 자주 사용하는 멤버에 0을 할당합니다.  첫 번째 열거형 멤버의 값이 선언에서 설정되지 않으면 기본적으로 그 값은 0입니다.  
  
 <xref:System.FlagsAttribute>가 적용된 열거형에서 0 값을 가진 멤버를 정의하는 경우 열거형에 값이 설정되지 않았음을 나타낼 수 있도록 이름이 'None'이어야 합니다.  0 값을 가진 멤버를 다른 용도로 사용하는 것은 해당 멤버에 AND 및 OR 비트 연산자를 사용할 수 없다는 점에서 <xref:System.FlagsAttribute>를 사용하는 것과 반대됩니다.  이것은 하나의 멤버에만 0 값을 할당해야 한다는 의미입니다.  플래그 특성을 사용하는 열거형에 0 값을 가진 멤버가 여러 개 있으면 `Enum.ToString()`은 0이 아닌 멤버에 대해 올바르지 않은 결과를 반환합니다.  
  
## 위반 문제를 해결하는 방법  
 플래그 특성을 사용하지 않는 열거형에서 발생하는 이 규칙 위반 문제를 해결하려면 0 값을 가진 멤버를 정의합니다. 이것은 주요 변경에 해당하지 않습니다.  0 값을 가진 멤버를 정의하고 플래그 특성을 사용하는 열거형의 경우 이 멤버의 이름을 'None'으로 지정하고 0 값을 가진 다른 멤버는 모두 삭제합니다. 이것은 주요 변경에 해당합니다.  
  
## 경고를 표시하지 않는 경우  
 이전에 제공된 플래그 특성을 사용하는 열거형 이외에는 이 규칙에서 경고를 표시하지 않도록 설정하지 마십시오.  
  
## 예제  
 다음 예제에서는 규칙을 충족하는 두 개의 열거형과 규칙을 위반하는 열거형 `BadTraceOptions`를 보여 줍니다.  
  
 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
 [!code-cs[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
 [!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]  
  
## 관련 규칙  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: 열거형 값의 이름을 'Reserved'로 지정하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: 열거형 저장소는 Int32여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## 참고 항목  
 <xref:System.Enum?displayProperty=fullName>