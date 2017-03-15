---
title: "CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TestForEmptyStringsUsingStringLength"
  - "CA1820"
helpviewer_keywords: 
  - "TestForEmptyStringsUsingStringLength"
  - "CA1820"
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 21
---
# CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TestForEmptyStringsUsingStringLength|  
|CheckId|CA1820|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Object.Equals%2A?displayProperty=fullName>를 사용하여 문자열을 빈 문자열과 비교했습니다.  
  
## 규칙 설명  
 <xref:System.String.Length%2A?displayProperty=fullName> 속성 또는 <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> 메서드를 사용하여 문자열을 비교하면 <xref:System.Object.Equals%2A>를 사용할 때보다 훨씬 빠릅니다.  이것은 <xref:System.Object.Equals%2A>가 <xref:System.String.Length%2A> 속성 값을 검색하여 이를 0과 비교하는 명령의 개수나 <xref:System.String.IsNullOrEmpty%2A>보다 훨씬 많은 MSIL 명령을 실행하기 때문입니다.  
  
 <xref:System.Object.Equals%2A>와 <xref:System.String.Length%2A> \=\= 0은 null 문자열에 대해 서로 다르게 동작합니다.  null 문자열에 대해 <xref:System.String.Length%2A> 속성 값을 가져오려고 하면 공용 언어 런타임에서 <xref:System.NullReferenceException?displayProperty=fullName>을 throw합니다.  null 문자열과 빈 문자열을 비교하면 공용 언어 런타임에서는 예외를 throw하지 않으며 `false`가 반환됩니다.  null 테스트의 경우에는 두 방법의 상대적인 성능에 큰 차이가 없습니다.  [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]을 대상으로 하는 경우 <xref:System.String.IsNullOrEmpty%2A> 메서드를 사용합니다.  그 밖의 경우에는 가급적이면 <xref:System.String.Length%2A> \=\= 비교를 사용합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 비교할 때 <xref:System.String.Length%2A> 속성을 사용하고 null 문자열을 테스트하도록 변경합니다.  [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]을 대상으로 하는 경우 <xref:System.String.IsNullOrEmpty%2A> 메서드를 사용합니다.  
  
## 경고를 표시하지 않는 경우  
 성능 문제가 그다지 중요하지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 빈 문자열을 찾는 데 사용되는 다양한 기술을 보여 줍니다.  
  
 [!CODE [FxCop.Performance.StringTest#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest#1)]