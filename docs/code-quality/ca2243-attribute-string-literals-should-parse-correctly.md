---
title: "CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2243"
  - "AttributeStringLiteralsShouldParseCorrectly"
helpviewer_keywords: 
  - "AttributeStringLiteralsShouldParseCorrectly"
  - "CA2243"
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AttributeStringLiteralsShouldParseCorrectly|  
|CheckId|CA2243|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 특성의 문자열 리터럴 매개 변수가 URL, GUID 또는 버전에 대해 구문을 올바르게 분석하지 않습니다.  
  
## 규칙 설명  
 특성은 <xref:System.Attribute?displayProperty=fullName>에서 파생 되었고, 컴파일할 때 특성이 사용되므로 상수 값만 해당 생성자로 전달될 수 있습니다.  이러한 형식은 상수로 나타낼 수 없으므로 URL, GUID 및 버전을 나타내야 하는 특성 매개 변수는 <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName> 및 <xref:System.Version?displayProperty=fullName>으로 입력할 수 없습니다.  대신 문자열로 나타내야 합니다.  
  
 매개 변수는 문자열로 입력되므로 컴파일할 때 잘못된 형식의 매개 변수가 전달될 수 있습니다.  
  
 이 규칙은 명명 방법을 사용하여 URI\(Uniform Resource Identifier\), GUID\(Globally Unique Identifier\) 또는 버전을 나타내는 매개 변수를 찾고 전달된 값이 올바른지 확인합니다.  
  
## 위반 문제를 해결하는 방법  
 매개 변수 문자열을 올바른 형식의 URL, GUID 또는 버전으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 매개 변수가 URL, GUID 또는 버전을 나타내지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 AssemblyFileVersionAttribute에 대한 코드를 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]  
  
 이 규칙은 다음과 같은 매개 변수에 의해 트리거됩니다.  
  
-   ‘버전’이 포함되어 있고 System.Version으로 구문 분석할 수 없는 매개 변수  
  
-   ‘guid’가 포함되어 있고 System.Guid로 구문 분석할 수 없는 매개 변수  
  
-   ‘uri’, 'urn' 또는 ‘url’이 포함되어 있고 System.Uri로 구문 분석할 수 없는 매개 변수  
  
## 참고 항목  
 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)