---
title: "CA1722: 식별자에는 올바른 접두사를 사용해야 합니다. | Microsoft Docs"
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
  - "IdentifiersShouldNotHaveIncorrectPrefix"
  - "CA1722"
helpviewer_keywords: 
  - "CA1722"
  - "IdentifiersShouldNotHaveIncorrectPrefix"
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1722: 식별자에는 올바른 접두사를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|  
|CheckId|CA1722|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 식별자에 잘못된 접두사가 있습니다.  
  
## 규칙 설명  
 규칙에 따라 특정 프로그래밍 요소에만 특정 접두사로 시작하는 이름을 사용할 수 있습니다.  
  
 형식 이름에는 특정 접두사가 없으며 'C' 접두사를 사용하면 안 됩니다.  이 규칙에서는 'CMyClass'와 같은 형식 이름에 대해서는 위반을 보고하고 'Cache'와 같은 형식 이름에 대해서는 위반을 보고하지 않습니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 식별자에서 접두사를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 관련 규칙  
 [CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)