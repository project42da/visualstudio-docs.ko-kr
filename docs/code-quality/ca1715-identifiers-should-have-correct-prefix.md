---
title: "CA1715: 식별자에는 올바른 접두사를 사용해야 합니다. | Microsoft Docs"
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
  - "CA1715"
  - "IdentifiersShouldHaveCorrectPrefix"
helpviewer_keywords: 
  - "IdentifiersShouldHaveCorrectPrefix"
  - "CA1715"
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectPrefix|  
|CheckId|CA1715|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 \- 인터페이스에서 발생한 경우<br /><br /> 주요 변경 아님 \- 제네릭 형식 매개 변수에서 발생한 경우|  
  
## 원인  
 외부에 노출되는 인터페이스의 이름이 대문자 "I"로 시작하지 않습니다.  
  
 또는  
  
 외부에 노출되는 형식 또는 메서드의 제네릭 형식 매개 변수 이름이 대문자 "T"로 시작하지 않습니다.  
  
## 규칙 설명  
 규칙에 따라 특정 프로그래밍 요소의 이름은 특정 접두사로 시작합니다.  
  
 인터페이스 이름은 대문자 'I'로 시작하고 그 다음에 다른 대문자가 와야 합니다.  이 규칙에서는 'MyInterface' 및 'IsolatedInterface' 같은 인터페이스 이름에 대한 위반을 보고합니다.  
  
 제네릭 형식 매개 변수 이름은 대문자 'T'로 시작해야 하고 필요에 따라 그 다음에 다른 대문자가 올 수 있습니다.  이 규칙에서는 'V' 및 'Type'과 같은 제네릭 형식 매개 변수 이름에 대한 위반을 보고합니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 식별자의 이름을 올바른 접두사를 사용하도록 다시 지정합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 **다음 예제에서는 이름이 잘못된 인터페이스를 보여 줍니다.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
 [!code-cs[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]  
  
## 예제  
 **다음 예제에서는 인터페이스 이름 앞에 'I'를 추가하여 위에 나와 있는 규칙 위반을 해결합니다.**  
  
 [!code-cs[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]  
  
## 예제  
 **다음 예제에서는 이름이 잘못된 제네릭 형식 매개 변수를 보여 줍니다.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
 [!code-cs[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]  
  
## 예제  
 **다음 예제에서는 제네릭 형식 매개 변수 이름 앞에 'T'를 추가하여 위에 나와 있는 규칙 위반을 해결합니다.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
 [!code-cs[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]  
  
## 관련 규칙  
 [CA1722: 식별자에는 올바른 접두사를 사용해야 합니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)