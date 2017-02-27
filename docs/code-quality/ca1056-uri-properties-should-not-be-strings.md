---
title: "CA1056: URI 속성은 문자열이면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UriPropertiesShouldNotBeStrings"
  - "CA1056"
helpviewer_keywords: 
  - "CA1056"
  - "UriPropertiesShouldNotBeStrings"
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# CA1056: URI 속성은 문자열이면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UriPropertiesShouldNotBeStrings|  
|CheckId|CA1056|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 형식이 이름에 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"이 포함된 문자열 속성을 선언합니다.  
  
## 규칙 설명  
 이 규칙에서는 속성 이름을 파스칼식 대\/소문자 구분 규칙에 따라 토큰으로 분할하고 각 토큰이 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"과 같은지 여부를 확인합니다.  일치하는 항목이 있으면 규칙에서는 속성이 URI\(Uniform Resource Identifier\)를 나타낸다고 가정합니다.  URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다.  <xref:System.Uri?displayProperty=fullName> 클래스는 이러한 서비스를 안전한 방식으로 제공합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 속성을 <xref:System.Uri> 형식으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 속성이 URI를 나타내지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 `ErrorProne` 형식과 이 규칙을 만족하는 `SaferWay` 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1056-uri-properties-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1056-uri-properties-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1056-uri-properties-should-not-be-strings_1.cpp)]  
  
## 관련 규칙  
 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../Topic/CA2234:%20Pass%20System.Uri%20objects%20instead%20of%20strings.md)  
  
 [CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)