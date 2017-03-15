---
title: "CA1014: CLSCompliantAttribute로 어셈블리 표시 | Microsoft Docs"
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
  - "CA1014"
  - "MarkAssembliesWithClsCompliant"
helpviewer_keywords: 
  - "CA1014"
  - "MarkAssembliesWithClsCompliant"
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1014: CLSCompliantAttribute로 어셈블리 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkAssembliesWithClsCompliant|  
|CheckId|CA1014|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 어셈블리에 <xref:System.CLSCompliantAttribute?displayProperty=fullName> 특성이 적용되어 있지 않습니다.  
  
## 규칙 설명  
 CLS\(공용 언어 사양\)는 어셈블리가 여러 프로그래밍 언어에 사용될 경우 준수해야 하는 명명 제한, 데이터 형식 및 규칙을 정의합니다.  모든 어셈블리에는 <xref:System.CLSCompliantAttribute>를 통해 CLS 규격을 명시적으로 나타내는 것이 좋습니다.  어셈블리에 이 특성이 없으면 해당 어셈블리가 규격을 따르지 않습니다.  
  
 CLS 규격 어셈블리에는 CLS 규격을 따르지 않는 형식이나 형식 멤버가 포함될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 어셈블리에 해당 특성을 추가합니다.  전체 어셈블리를 비규격으로 표시하는 대신 규격을 따르지 않는 형식이나 형식 멤버를 확인하고 이들 요소를 비규격으로 표시해야 합니다.  가능하다면 많은 사용자가 어셈블리의 모든 기능에 액세스할 수 있도록 비규격 멤버에 대해 CLS 규격 대체 멤버를 제공해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  어셈블리가 규격을 따르지 않도록 하려면 해당 특성을 적용하고 그 값을 `false`로 설정합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.CLSCompliantAttribute?displayProperty=fullName> 특성을 적용하여 CLS 규격을 선언하는 어셈블리를 보여 줍니다.  
  
 [!code-cs[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]  
  
## 참고 항목  
 <xref:System.CLSCompliantAttribute?displayProperty=fullName>   
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)