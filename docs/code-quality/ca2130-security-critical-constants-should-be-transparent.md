---
title: "CA2130: 보안 위험 상수는 투명해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2130"
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# CA2130: 보안 위험 상수는 투명해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ConstantsShouldBeTransparent|  
|CheckId|CA2130|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 상수 필드 또는 열거형 멤버는 <xref:System.Security.SecurityCriticalAttribute>로 표시됩니다.  
  
## 규칙 설명  
 런타임에 조회가 필요하지 않도록 컴파일러에서 상수 값을 인라인하기 때문에 상수 값에 투명성이 적용되지 않습니다.  상수 필드는 보안 투명해야 하므로 코드 검토자는 투명 코드가 상수에 액세스할 수 없다고 가정하지 않습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 필드 또는 값에서 SecurityCritical 특성을 제거하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 열거형 값 `EnumWithCriticalValues.CriticalEnumValue` 및 상수 `CriticalConstant`가 이 경고를 발생시킵니다.  이 문제를 해결하려면 \[`SecurityCritical`\] 특성을 제거하여 보안을 투명하게 만드십시오.  
  
 [!code-cs[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]