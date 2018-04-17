---
title: ': Ca1714 플래그 열거형에는 복수형 이름을 사용 해야 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5dc35718a20743ce6ed1502dbd1d9ed3c8a626e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.
|||  
|-|-|  
|TypeName|FlagsEnumsShouldHavePluralNames|  
|CheckId|CA1714|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 열거형에는 <xref:System.FlagsAttribute?displayProperty=fullName> 이름과 끝나지 않는 및 s '.  
  
## <a name="rule-description"></a>규칙 설명  
 형식으로 표시 된 <xref:System.FlagsAttribute> 은 둘 이상의 값을 지정할 수 있음을 나타내므로 특성 복수형 이름을 갖습니다. 예를 들어 해당 주의 일을 정의 하는 열거형 수 사용 하려는 응용 프로그램에서 여러 날짜를 지정할 수 있습니다. 이 열거형 있어야는 <xref:System.FlagsAttribute> '일' 호출 될 수 없습니다. 하루를 지정할 수 있는 유사한 열거형에는 특성이 없으며 수 'Day'를 호출 합니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 열거형의 이름을 복수 단어를 만들거나 제거는 <xref:System.FlagsAttribute> 특성 경우 여러 열거 값을 동시에 지정 하지 않아야 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 이름이 복수 단어 이지만 끝나지 않는 위반을 보류 하려면 안전의 '. 예를 들어 이전에 설명 된 여러 날짜 열거형 '이었다 이름이 지정 된,이 규칙이 하지만 하지 의도 된 논리를 위반 것입니다. 이러한 위반은 표시 하지 않아야 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [열거형 디자인](/dotnet/standard/design-guidelines/enum)