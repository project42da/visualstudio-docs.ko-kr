---
title: "CA1823: 사용되지 않는 전용 필드를 사용하지 마십시오. | Microsoft Docs"
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
  - "AvoidUnusedPrivateFields"
  - "CA1823"
helpviewer_keywords: 
  - "AvoidUnusedPrivateFields"
  - "CA1823"
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1823: 사용되지 않는 전용 필드를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidUnusedPrivateFields|  
|CheckId|CA1823|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 코드에 전용 필드가 있지만 이를 사용하는 코드 경로가 없는 경우 이 규칙이 보고됩니다.  
  
## 규칙 설명  
 어셈블리에서 액세스되지 않는 것으로 보이는 전용 필드가 발견되었습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 필드를 제거하거나 해당 필드를 사용하는 코드를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../Topic/CA1812:%20Avoid%20uninstantiated%20internal%20classes.md)  
  
 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../Topic/CA1801:%20Review%20unused%20parameters.md)  
  
 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)  
  
 [CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](../code-quality/ca1811-avoid-uncalled-private-code.md)