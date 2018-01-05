---
title: "CA1027: 열거형을 FlagsAttribute로 표시 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9c80b90e1b1fe0ba89717a175666a68c3812665c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: 열거형을 FlagsAttribute로 표시하십시오.
|||  
|-|-|  
|TypeName|MarkEnumsWithFlags|  
|CheckId|CA1027|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 Public 열거형의 값은 2의 거듭제곱 또는 열거형에 정의 된 다른 값의 조합이 및 <xref:System.FlagsAttribute?displayProperty=fullName> 특성이 없으면 합니다. 거짓 긍정을 줄이기 위해이 규칙에는 연속 값을 가진 열거형에 대 한 위반을 보고 하지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 적용 <xref:System.FlagsAttribute> 열거형 명명된 된 상수를 의미 있게 조합할 수 있는 경우에 합니다. 추적 하는 요일 리소스를 사용할 수 있는 응용 프로그램에서 주 중 일의 열거형을 예로 들 수 있습니다. 각 리소스의 가용성을 된 열거형을 사용 하 여 인코딩된 경우 <xref:System.FlagsAttribute> 현재, 일의 조합을 나타낼 수 있습니다. 특성이 없으면 하루가 주의 나타낼 수 있습니다.  
  
 함께 사용할 수 있는 열거형이 저장 되는 필드에 각 열거형 값은 비트 필드에 그룹으로 처리 됩니다. 따라서 이러한 필드는 라고도 *비트 필드*합니다. 저장소는 비트 필드에 대 한 열거형 값을 결합 하려면 Boolean 조건부 연산자를 사용 합니다. 특정 열거형 값이 있는지 여부를 결정 하는 비트 필드를 테스트 하려면 부울 논리 연산자를 사용 합니다. 저장 하 고 결합 된 열거형 값을 제대로 검색을 비트 필드 열거형에 정의 된 각 값에는 2의 거듭제곱 이어야 합니다. 그렇지 않은, 부울 논리 연산자는 필드에 저장 된 각 열거형 값을 추출할 수 없습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 추가 <xref:System.FlagsAttribute> 의 열거형입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 열거형 값 조합을 허용 하지 않을 경우이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예  
 다음 예에서 `DaysEnumNeedsFlags` 사용 하기 위한 요구 사항을 충족 하는 열거형은 <xref:System.FlagsAttribute>, 이지만 포함 하지 않습니다. `ColorEnumShouldNotHaveFlag` 열거형에는 2의 거듭제곱 값 없지만 잘못 지정 <xref:System.FlagsAttribute>합니다. 이 규칙을 위반 [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)합니다.  
  
 [!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.FlagsAttribute?displayProperty=fullName>