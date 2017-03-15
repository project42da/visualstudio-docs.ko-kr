---
title: "CA1019: 특성 인수의 접근자를 정의하십시오. | Microsoft Docs"
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
  - "CA1019"
  - "DefineAccessorsForAttributeArguments"
helpviewer_keywords: 
  - "CA1019"
  - "DefineAccessorsForAttributeArguments"
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1019: 특성 인수의 접근자를 정의하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DefineAccessorsForAttributeArguments|  
|CheckId|CA1019|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 생성자에서 특성이 해당 속성이 없는 인수를 정의합니다.  
  
## 규칙 설명  
 특성에서는 대상에 특성을 적용할 때 지정해야 하는 필수 인수를 정의할 수 있습니다.  이러한 인수는 특성 생성자에 위치 매개 변수로 제공되기 때문에 이러한 인수를 위치 인수라고도 합니다.  모든 필수 인수에 대해 특성은 실행 시간에 인수의 값을 검색할 수 있도록 해당하는 읽기 전용 속성도 제공해야 합니다.  이 규칙에서는 각 생성자 매개 변수에 대해 해당 속성이 정의되었는지 확인합니다.  
  
 특성에서는 명명된 인수라고 하는 선택적 인수도 정의할 수 있습니다.  이들 인수는 이름으로 특성 생성자에 제공되며 해당하는 읽기\/쓰기 특성이 있어야 합니다.  
  
 필수 및 선택적 인수에 대해 해당 속성 및 생성자 매개 변수는 대\/소문자가 다른 동일한 이름을 사용해야 합니다.  속성에는 파스칼식 대\/소문자가 사용되고 매개 변수에는 카멜식 대\/소문자가 사용됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 읽기 전용 속성이 없는 각 생성자 매개 변수에 읽기 전용 속성을 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 필수 인수의 값을 검색할 수 없도록 하려면 이 규칙에서 경고를 표시하지 않도록 설정합니다.  
  
## 사용자 지정 특성 예제  
  
### 설명  
 다음 예제에서는 필수\(위치\) 매개 변수를 정의하는 두 개의 특성을 보여 줍니다.  특성의 첫 번째 구현은 잘못 정의하고  두 번째 구현은 올바르게 정의합니다.  
  
### 코드  
 [!code-cs[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
 [!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]  
  
## 위치 인수 및 명명된 인수  
  
### 설명  
 위치 인수와 명명된 인수는 라이브러리의 소비자에게 어떤 인수가 특성의 필수 인수이고 어떤 요소가 선택적 요소인지를 명확히 알려 줍니다.  
  
 다음 예제에서는 위치 인수와 명명된 인수를 모두 사용한 특성 구현을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]  
  
### 설명  
 다음 예제에서는 두 개의 속성에 사용자 지정 특성을 적용하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]  
  
## 관련 규칙  
 [CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## 참고 항목  
 [특성](../Topic/Attributes1.md)