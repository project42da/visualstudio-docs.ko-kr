---
title: "CA1700: 열거형 값의 이름을 &#39;Reserved&#39;로 지정하지 마십시오. | Microsoft Docs"
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
  - "CA1700"
  - "DoNotNameEnumValuesReserved"
helpviewer_keywords: 
  - "DoNotNameEnumValuesReserved"
  - "CA1700"
ms.assetid: 7a7e01c3-ae7d-4c82-a646-91b58864a749
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1700: 열거형 값의 이름을 &#39;Reserved&#39;로 지정하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotNameEnumValuesReserved|  
|CheckId|CA1700|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 열거형 멤버 이름에 "reserved"라는 단어가 포함되어 있습니다.  
  
## 규칙 설명  
 이 규칙에서는 "reserved"라는 단어가 포함된 이름을 갖는 열거형 멤버가 현재 사용되지는 않지만 이후 버전에서 이름이 바뀌거나 제거될 자리 표시자라고 가정합니다.  멤버의 이름을 바꾸거나 멤버를 제거하는 것은 주요 변경에 해당합니다.  사용자가 이름에 "reserved"가 포함되었다고 해서 해당 멤버를 무시하거나 설명서를 읽고 이를 따를 것이라고 기대하지는 마십시오.  또한 예약된 멤버는 개체 브라우저 및 스마트 통합 개발 환경에 표시되기 때문에 사용자는 어떤 멤버가 실제로 사용되는지 혼란스러울 수 있습니다.  
  
 예약된 멤버를 사용하는 대신 이후 버전에서는 새로운 멤버를 열거형에 추가합니다.  대부분의 경우 새 멤버를 추가하는 것은 원래 멤버의 값을 변경시키지만 않으면 주요 변경에 해당되지 않습니다.  
  
 원래 멤버의 값이 원래 값으로 유지되는 경우에 멤버 추가가 주요 변경에 해당되는 경우는 드뭅니다.  기본적으로 전체 멤버 목록을 포함하고 기본 case에 예외를 throw하는 반환 값에 대해 `switch`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 `Select`\) 문을 사용하는 호출자를 중단하지 않고서는 기존 코드 경로에서 새 멤버를 반환할 수 없습니다.  두 번째로 고려해야 할 점은 클라이언트 코드가 <xref:System.Enum.IsDefined%2A?displayProperty=fullName> 같은 리플렉션 메서드에서 변경된 동작을 처리하지 못할 수 있다는 것입니다.  따라서 기존 메서드에서 새 멤버를 반환해야 하거나 제한된 리플렉션 사용으로 인해 알려진 응용 프로그램 비호환성 문제가 있을 경우 유일한 해결책은 다음과 같습니다.  
  
1.  원래 멤버와 새 멤버를 포함하는 새 열거형을 추가합니다.  
  
2.  원래 열거형을 <xref:System.ObsoleteAttribute?displayProperty=fullName> 특성으로 표시합니다.  
  
 원래 열거형을 노출하는, 외부에서 볼 수 있는 형식이나 멤버에 대해서도 이와 같은 절차를 따르십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 해당 멤버를 제거하거나 멤버의 이름을 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 이전에 제공된 라이브러리의 경우 또는 멤버가 현재 사용되는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: 열거형 저장소는 Int32여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1008: 열거형에는 0 값이 있어야 합니다.](../code-quality/ca1008-enums-should-have-zero-value.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)