---
title: "CA1034: 중첩 형식은 노출하지 마십시오. | Microsoft Docs"
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
  - "NestedTypesShouldNotBeVisible"
  - "CA1034"
helpviewer_keywords: 
  - "NestedTypesShouldNotBeVisible"
  - "CA1034"
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1034: 중첩 형식은 노출하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|NestedTypesShouldNotBeVisible|  
|CheckId|CA1034|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 형식에 외부에서 볼 수 있는 형식 선언이 들어 있습니다.  중첩 열거형 및 Protected 형식은 이 규칙에서 예외입니다.  
  
## 규칙 설명  
 중첩 형식은 다른 형식의 범위 내에 선언된 형식입니다.  중첩 형식은 포함하는 형식의 private 구현 정보를 캡슐화하는 데 유용합니다.  이 용도로 사용할 경우 중첩 형식은 외부에 노출되면 안 됩니다.  
  
 이름 충돌을 피하거나 논리적 그룹화를 수행하려면 외부에서 볼 수 있는 중첩 형식을 사용하지 말고 대신 네임스페이스를 사용하십시오.  
  
 중첩 형식에는 멤버 액세스 가능성의 개념이 포함되어 있는데, 모든 프로그래머가 이 개념을 명확하게 이해하고 있는 것은 아닙니다.  
  
 Protected 형식은 미리 사용자 지정한 시나리오의 서브클래스 및 중첩 형식에서 사용할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 중첩 형식을 외부에 표시할 계획이 아니면 형식의 액세스 가능성을 변경합니다.  그렇지 않으면 중첩 형식을 해당 부모에서 제거합니다.  중첩의 목적이 중첩 형식을 분류하는 것이라면 네임스페이스를 대신 사용하여 계층 구조를 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-cs[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]