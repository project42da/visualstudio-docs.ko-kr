---
title: "CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다. | Microsoft Docs"
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
  - "ParameterNamesShouldNotMatchMemberNames"
  - "CA1719"
helpviewer_keywords: 
  - "CA1719"
  - "ParameterNamesShouldNotMatchMemberNames"
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ParameterNamesShouldNotMatchMemberNames|  
|CheckId|CA1719|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 멤버의 이름이 대\/소문자를 구분하지 않을 경우 해당 매개 변수 중 하나의 이름과 일치합니다.  
  
## 규칙 설명  
 매개 변수 이름은 매개 변수의 의미를 나타내고 멤버 이름은 멤버의 의미를 나타내야 합니다.  매개 변수와 멤버의 의미가 같게 디자인되는 경우는 드뭅니다.  매개 변수의 이름을 멤버 이름과 동일하게 지정하는 것은 비직관적이고 라이브러리 사용을 어렵게 만듭니다.  
  
## 위반 문제를 해결하는 방법  
 멤버 이름과 일치하지 않는 매개 변수 이름을 선택합니다.  
  
## 경고를 표시하지 않는 경우  
 새로 개발하는 경우 이 규칙에서 경고를 표시하지 않아야 하는 시나리오는 알려져 있지 않습니다.  제공되는 라이브러리의 경우에는 이 규칙에서 경고를 표시하지 않아야 할 수 있습니다.  
  
## 관련 규칙  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)