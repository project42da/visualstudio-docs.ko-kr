---
title: "CA1011: 기본 형식을 매개 변수로 전달해 보십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ConsiderPassingBaseTypesAsParameters"
  - "CA1011"
helpviewer_keywords: 
  - "CA1011"
  - "ConsiderPassingBaseTypesAsParameters"
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1011: 기본 형식을 매개 변수로 전달해 보십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ConsiderPassingBaseTypesAsParameters|  
|CheckId|CA1011|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드 선언에 파생 형식인 정식 매개 변수가 포함되어 있고 메서드가 매개 변수의 기본 형식인 멤버만 호출합니다.  
  
## 규칙 설명  
 기본 형식이 메서드 선언의 매개 변수로 지정된 경우 기본 형식에서 파생된 모든 형식을 해당 인수로 메서드에 전달할 수 있습니다.  메서드 본문 안에서 인수가 사용될 경우 실행되는 특정 메서드는 인수의 형식에 따라 달라집니다.  파생 형식에서 제공하는 추가 기능이 필요하지 않을 경우 기본 형식을 사용하면 메서드를 보다 광범위하게 사용할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 매개 변수의 형식을 기본 형식으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  
  
-   파생된 형식에서 제공하는 특정 기능이 메서드에 필요한 경우  
  
     \- 또는 \-  
  
-   파생된 형식만 또는 파생된 추가 형식을 메서드에 전달되도록 하려면.  
  
 이 경우 컴파일러 및 런타임에서 제공하는 강력한 형식 검사로 인해 코드가 더욱 강력해집니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IO.FileStream> 개체에서만 사용할 수 있는 `ManipulateFileStream` 메서드에서 이 규칙을 위반하는 예를 보여 줍니다.  두 번째 메서드인 `ManipulateAnyStream`은 <xref:System.IO.FileStream> 매개 변수를 <xref:System.IO.Stream>으로 바꿔 이 규칙을 만족시킵니다.  
  
 [!code-cs[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]  
  
## 관련 규칙  
 [CA1059: 멤버는 구체적인 특정 형식을 노출하면 안 됩니다.](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)