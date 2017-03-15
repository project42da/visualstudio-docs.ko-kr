---
title: "CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1702"
  - "CompoundWordsShouldBeCasedCorrectly"
helpviewer_keywords: 
  - "CA1702"
  - "CompoundWordsShouldBeCasedCorrectly"
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CompoundWordsShouldBeCasedCorrectly|  
|CheckId|CA1702|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 \- 어셈블리에서 발생한 경우,<br /><br /> 주요 변경 아님 \- 형식 매개 변수에서 발생한 경우|  
  
## 원인  
 식별자 이름에 여러 개의 단어가 포함되어 있으며 이 중 적어도 하나의 단어가 대\/소문자를 정확하게 사용하지 않은 복합 단어인 것 같습니다.  
  
## 규칙 설명  
 식별자 이름은 대\/소문자에 따라 단어로 구분됩니다.  Microsoft 맞춤법 검사 라이브러리에서는 연속된 각 두 단어의 조합을 검사합니다.  규칙 위반이 인식되면 식별자에서 규칙 위반을 작성합니다.  규칙을 위반하는 복합 단어의 예로는 "CheckSum" 및 "MultiPart"가 있습니다. 이 두 단어는 각각 "Checksum"과 "Multipart"로 대\/소문자를 표기해야 합니다.  일반적으로 이러한 방식으로 사용되므로 이 규칙에는 몇 가지 예외가 적용되며, 두 개의 개별적인 단어\(예: "ToolBar", "FileName"\)로 표기해야 하는 "Toolbar" 및 "Filename" 등의 몇 가지 단일 단어에 플래그가 지정됩니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 정확한 대\/소문자를 사용하도록 이름을 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 맞춤법 사전에서 복합 단어의 각 부분을 인식할 수 있고 두 단어로 사용하려는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1701: 리소스 문자열 복합 단어는 정확한 대\/소문자를 사용해야 합니다.](../Topic/CA1701:%20Resource%20string%20compound%20words%20should%20be%20cased%20correctly.md)  
  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## 참고 항목  
 [명명 지침](../Topic/Naming%20Guidelines.md)   
 [대\/소문자 표기법](../Topic/Capitalization%20Conventions.md)