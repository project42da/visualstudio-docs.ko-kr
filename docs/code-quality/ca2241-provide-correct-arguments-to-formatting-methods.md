---
title: "CA2241: 형식 메서드에 올바른 인수를 제공하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2241"
  - "Provide correct arguments to formatting methods"
  - "ProvideCorrectArgumentsToFormattingMethods"
helpviewer_keywords: 
  - "CA2241"
  - "ProvideCorrectArgumentsToFormattingMethods"
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# CA2241: 형식 메서드에 올바른 인수를 제공하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ProvideCorrectArgumentsToFormattingMethods|  
|CheckId|CA2241|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Console.WriteLine%2A>,  <xref:System.Console.Write%2A> 또는 <xref:System.String.Format%2A?displayProperty=fullName> 같은 메서드에 전달되는 `format` 문자열 인수에 각 개체 인수에 해당하는 형식 항목이 없거나 각 형식 항목에 해당하는 개체 인수가 없습니다.  
  
## 규칙 설명  
 <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A> 및 <xref:System.String.Format%2A> 같은 메서드에 대한 인수는 서식 문자열과 여러 개의 <xref:System.Object?displayProperty=fullName> 인스턴스로 구성됩니다.  서식 문자열은 텍스트와 {index\[,alignment\]\[:formatString\]} 형태의 포함된 서식 지정 항목으로 구성됩니다. index'는 서식을 지정할 개체를 나타내는 정수\(0부터 시작\)입니다.  개체에 서식 문자열의 해당 인덱스가 없으면 해당 개체는 무시됩니다.  'index'로 지정된 개체가 없으면 런타임에 <xref:System.FormatException?displayProperty=fullName>이 throw됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 각 개체 인수에 서식 지정 항목을 지정하고 각 서식 지정 항목에 개체 인수를 지정합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 두 가지 경우를 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-cs[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]