---
title: "CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다. | Microsoft Docs"
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
  - "CA1057"
  - "StringUriOverloadsCallSystemUriOverloads"
helpviewer_keywords: 
  - "StringUriOverloadsCallSystemUriOverloads"
  - "CA1057"
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|StringUriOverloadsCallSystemUriOverloads|  
|CheckId|CA1057|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식이 문자열 매개 변수를 <xref:System.Uri?displayProperty=fullName> 매개 변수로만 바꾸어서 다른 메서드 오버로드를 선언하고, 문자열 매개 변수를 사용하는 오버로드가 <xref:System.Uri> 매개 변수를 사용하는 오버로드를 호출하지 않습니다.  
  
## 규칙 설명  
 오버로드가 문자열\/<xref:System.Uri> 매개 변수만 다르므로 문자열이 URI\(Uniform Resource Identifier\)를 나타내는 것으로 간주됩니다.  URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다.  <xref:System.Uri> 클래스는 이러한 서비스를 안전한 방식으로 제공합니다.  <xref:System.Uri> 클래스의 이점을 활용하려면 문자열 오버로드가 문자열 인수를 사용하여 <xref:System.Uri> 오버로드를 호출해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 문자열 인수를 사용하여 <xref:System.Uri> 클래스의 인스턴스를 만들도록 URI의 문자열 표현을 사용하는 메서드를 다시 구현한 다음 <xref:System.Uri> 매개 변수가 있는 오버로드에 <xref:System.Uri> 개체를 전달합니다.  
  
## 경고를 표시하지 않는 경우  
 문자열 매개 변수가 URI를 나타내지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 올바르게 구현된 문자열 오버로드를 보여 줍니다.  
  
 [!CODE [FxCop.Design.CallUriOverload#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload#1)]  
  
## 관련 규칙  
 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../Topic/CA2234:%20Pass%20System.Uri%20objects%20instead%20of%20strings.md)  
  
 [CA1056: URI 속성은 문자열이면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)