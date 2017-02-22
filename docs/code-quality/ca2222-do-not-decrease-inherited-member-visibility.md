---
title: "CA2222: 상속된 멤버 노출 수준을 낮추지 마십시오. | Microsoft Docs"
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
  - "DoNotDecreaseInheritedMemberVisibility"
  - "CA2222"
helpviewer_keywords: 
  - "CA2222"
  - "DoNotDecreaseInheritedMemberVisibility"
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2222: 상속된 멤버 노출 수준을 낮추지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDecreaseInheritedMemberVisibility|  
|CheckId|CA2222|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 unsealed 형식의 private 메서드에 기본 형식에서 선언된 public 메서드와 동일한 시그너처가 있습니다.  private 메서드가 final이 아닙니다.  
  
## 규칙 설명  
 상속된 멤버에 대한 액세스 한정자는 변경하면 안 됩니다.  상속된 멤버를 private으로 변경하더라도 호출자가 메서드의 기본 클래스 구현에 액세스하는 것을 막을 수 없습니다.  멤버가 private이고 형식이 unsealed인 경우 상속 형식은 상속 계층 구조에 있는 메서드의 마지막 public 구현을 호출할 수 있습니다.  액세스 한정자를 변경해야 하는 경우에는 메서드 재정의를 방지하기 위해 메서드를 final로 표시하거나 해당 형식을 sealed로 지정해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 액세스 한정자를 private이 아닌 액세스 한정자로 변경합니다.  또는 프로그래밍 언어에서 지원하는 경우 메서드를 final로 지정합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/VisualBasic/ca2222-do-not-decrease-inherited-member-visibility_1.vb)]
 [!code-cs[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/CSharp/ca2222-do-not-decrease-inherited-member-visibility_1.cs)]