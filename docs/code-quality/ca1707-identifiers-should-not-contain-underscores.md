---
title: "CA1707: 식별자에는 밑줄을 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IdentifiersShouldNotContainUnderscores"
  - "CA1707"
helpviewer_keywords: 
  - "CA1707"
  - "IdentifiersShouldNotContainUnderscores"
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA1707: 식별자에는 밑줄을 사용할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 \- 어셈블리에서 발생한 경우,<br /><br /> 주요 변경 아님 \- 형식 매개 변수에서 발생한 경우|  
  
## 원인  
 식별자의 이름에 밑줄 문자\(\_\)가 있습니다.  
  
## 규칙 설명  
 규칙에 따라 식별자 이름에는 밑줄 문자\(\_\)가 포함될 수 없습니다.  이 규칙에서는 네임스페이스, 형식, 멤버 및 매개 변수를 검사합니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 이름에서 밑줄 문자를 모두 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 관련 규칙  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)