---
title: "CA1802: 가능하면 리터럴을 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UseLiteralsWhereAppropriate"
  - "CA1802"
helpviewer_keywords: 
  - "UseLiteralsWhereAppropriate"
  - "CA1802"
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1802: 가능하면 리터럴을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseLiteralsWhereAppropriate|  
|CheckId|CA1802|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 필드가 `static` 및 `readonly`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Shared` 및 `ReadOnly`\)로 선언되었으며 컴파일 타임에 계산할 수 있는 값으로 초기화됩니다.  
  
## 규칙 설명  
 선언 형식의 정적 생성자가 호출되는 경우 `static` `readonly` 필드의 값은 런타임에 계산됩니다.  `static` `readonly` 필드가 선언될 때 초기화되고 정적 생성자가 명시적으로 선언되지 않은 경우 컴파일러에서는 필드를 초기화하는 정적 생성자를 내보냅니다.  
  
 `const` 필드의 값은 컴파일 타임에 계산되고 메타데이터에 저장되므로 `static` `readonly` 필드에 비해 런타임 성능이 향상됩니다.  
  
 대상으로 지정된 필드에 할당되는 값을 컴파일 타임에 계산할 수 있으므로 값이 런타임이 아닌 컴파일 타임에 계산되도록 선언을 `const` 필드로 변경합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 `static` 및 `readonly` 한정자를 `const` 한정자로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 성능이 중요하지 않은 경우에는 이 규칙에서 경고를 표시하지 않거나 이 규칙을 사용하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식인 `UseReadOnly`와 규칙을 충족하는 형식인 `UseConstant`를 보여 줍니다.  
  
 [!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
 [!code-cs[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]