---
title: "CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오. | Microsoft Docs"
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
  - "CA1051"
  - "DoNotDeclareVisibleInstanceFields"
helpviewer_keywords: 
  - "CA1051"
  - "DoNotDeclareVisibleInstanceFields"
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDeclareVisibleInstanceFields|  
|CheckId|CA1051|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 형식에 외부에서 볼 수 있는 인스턴스 필드가 있습니다.  
  
## 규칙 설명  
 필드의 주된 용도는 구현을 세부적으로 설명하는 것입니다.  필드는 `private` 또는 `internal`이어야 하고 속성을 통해 노출되어야 합니다.  속성에 액세스하는 것은 필드에 액세스하는 것만큼 쉬우며 형식의 기능이 주요 변경 없이 확장되면 속성의 접근자에 있는 코드를 변경할 수 있습니다 주요 변경 내용을 변경할 수 있습니다.  private 또는 internal 필드의 값을 반환하기만 하는 속성은 필드 액세스와 동일하게 수행되도록 최적화됩니다. 따라서 속성 대신 외부에서 볼 수 있는 필드를 사용해도 성능상 이점은 거의 없습니다.  
  
 외부에서 볼 수 있다는 것은 `public`, `protected` 및 `protected internal`\(Visual Basic의 경우 `Public`, `Protected` 및 `Protected Friend`\) 액세스 가능성 수준을 나타냅니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 필드를 `private` 또는 `internal`로 지정하고 외부에서 볼 수 있는 속성을 사용하여 노출시킵니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  외부에서 볼 수 있는 필드에서 제공하는 이점은 속성에도 적용됩니다.  또한 공용 필드는 [링크 요청](../Topic/Link%20Demands.md)으로 보호될 수 없습니다.  [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식 \(`BadPublicInstanceFields`\)을 보여 줍니다.  `GoodPublicInstanceFields`는 올바른 코드를 표시합니다.  
  
 [!code-cs[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]  
  
## 관련 규칙  
 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
## 참고 항목  
 [링크 요청](../Topic/Link%20Demands.md)