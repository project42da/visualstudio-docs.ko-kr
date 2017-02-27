---
title: "CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IdentifiersShouldBeCasedCorrectly"
  - "CA1709"
helpviewer_keywords: 
  - "CA1709"
  - "IdentifiersShouldBeCasedCorrectly"
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 29
---
# CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldBeCasedCorrectly|  
|CheckId|CA1709|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 \- 어셈블리, 네임스페이스, 형식, 멤버 및 매개 변수에서 발생한 경우<br /><br /> 주요 변경 아님 \- 제네릭 형식 매개 변수에서 발생한 경우|  
  
## 원인  
 식별자 이름에 정확한 대\/소문자가 사용되지 않았습니다.  
  
 \- 또는 \-  
  
 식별자의 이름에 두 개의 문자로 구성된 머리글자어가 포함되어 있고 두 번째 문자가 소문자입니다.  
  
 \- 또는 \-  
  
 식별자의 이름에 셋 이상의 대문자로 구성된 머리글자어가 포함되어 있습니다.  
  
## 규칙 설명  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
 규칙에 따라 매개 변수 이름에는 카멜식 대\/소문자 구분을 사용하고 네임스페이스, 형식 및 멤버 이름에는 파스칼식 대\/소문자 구분을 사용합니다.  카멜식으로 대\/소문자가 구분된 이름에서는 첫 번째 문자가 소문자이고 나머지 단어의 첫 번째 문자가 대문자입니다.  카멜식으로 대\/소문자가 구분된 이름의 예로는 "packetSniffer", "ioFile", "fatalErrorCode" 등을 들 수 있습니다.  파스칼식으로 대\/소문자가 구분된 이름에서는 첫 번째 문자가 대문자이고 나머지 단어의 첫 번째 문자가 대문자입니다.  파스칼식으로 대\/소문자가 구분된 이름의 예로는 "PacketSniffer", "IOFile", "FatalErrorCode" 등을 들 수 있습니다.  
  
 이 규칙에서는 대\/소문자에 따라 이름을 단어로 나누고 두 글자로 이루어진 단어를 "In" 또는 "My" 같은 일반적인 두 글자 단어 목록에서 확인합니다.  일치하는 항목이 없을 경우 해당 단어는 머리글자어로 간주됩니다.  또한 이 규칙에서는 이름에 연속된 네 개의 대문자가 있거나 이름 끝에 연속된 세 개의 대문자가 있으면 머리글자어가 있는 것으로 간주합니다.  
  
 규칙에 따라 두 개의 문자로 구성된 머리글자어는 모두 대문자를 사용하고 셋 이상의 문자로 구성된 머리글자어는 파스칼식 대\/소문자 구분을 사용합니다.  이 명명 규칙을 사용하는 예로는 'DB', 'CR', 'Cpa', 'Ecma' 등을 들 수 있습니다.  이 규칙을 위반하는 예로는 'Io', 'XML', 'DoD' 등을 들 수 있으며 매개 변수가 아닌 이름의 예로는 'xp' 및 'cpl'을 들 수 있습니다.  
  
 'ID'는 이 규칙을 위반하는 특별한 경우입니다. 'Id'는 머리글자어가 아니라 'identification'의 약어입니다.  
  
## 위반 문제를 해결하는 방법  
 정확한 대\/소문자를 사용하도록 이름을 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 사용자의 고유 명명 규칙이 있거나 식별자가 회사 또는 기술 이름 등의 고유 명사를 나타내는 경우 이 경고를 표시하지 않아도 안전합니다.  
  
 코드 분석 사용자 지정 사전에 특정 용어, 약어 및 머리글자어를 추가할 수도 있습니다.  사용자 지정 사전에 지정된 용어에서는 이 규칙 위반이 발생하지 않습니다.  자세한 내용은 [방법: 코드 분석 사전 사용자 지정](../Topic/How%20to:%20Customize%20the%20Code%20Analysis%20Dictionary.md)을 참조하십시오.  
  
## 관련 규칙  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)