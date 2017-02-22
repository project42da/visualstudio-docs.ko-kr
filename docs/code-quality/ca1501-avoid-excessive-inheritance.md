---
title: "CA1501: 상속성을 너무 많이 사용하지 마십시오. | Microsoft Docs"
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
  - "CA1501"
  - "AvoidExcessiveInheritance"
helpviewer_keywords: 
  - "AvoidExcessiveInheritance"
  - "CA1501"
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1501: 상속성을 너무 많이 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidExcessiveInheritance|  
|CheckId|CA1501|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경|  
  
## 원인  
 형식이 상속 계층 구조에서 네 단계보다 아래에 있습니다.  
  
## 규칙 설명  
 여러 번 중첩된 형식 계층 구조는 추적하고, 이해하고, 유지 관리하기가 어렵습니다.  이 규칙에서는 분석을 같은 모듈의 계층 구조로 제한합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 상속 계층 구조 중 비교적 위에 있는 기본 형식에서 형식을 파생시키거나 중간 기본 형식 중 일부를 제거하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  그러나 코드를 관리하기가 더욱 어려워질 수 있습니다.  이 규칙 위반 문제를 해결할 경우 기본 형식의 표시 유형에 따라 주요 변경 내용이 생길 수 있습니다.  예를 들어, 공용 기본 형식을 제거하는 것은 주요 변경 내용에 해당합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]