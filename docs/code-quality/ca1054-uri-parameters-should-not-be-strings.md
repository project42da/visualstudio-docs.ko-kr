---
title: "CA1054: URI 매개 변수는 문자열이면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1054"
  - "UriParametersShouldNotBeStrings"
helpviewer_keywords: 
  - "CA1054"
  - "UriParametersShouldNotBeStrings"
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 14
---
# CA1054: URI 매개 변수는 문자열이면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UriParametersShouldNotBeStrings|  
|CheckId|CA1054|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 형식이 이름에 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"가 포함된 문자열 매개 변수가 있는 메서드를 선언한 다음 <xref:System.Uri?displayProperty=fullName> 매개 변수를 사용하는 해당 오버로드를 선언하지 않습니다.  
  
## 규칙 설명  
 이 규칙에서는 매개 변수 이름을 카멜식 대\/소문자 규칙에 따라 토큰으로 분할하고 각 토큰이 "uri", "Uri", "urn", "Urn", "url" 또는 "Url"과 같은지 여부를 확인합니다.  일치하는 항목이 있으면 규칙에서는 매개 변수가 URI\(Uniform Resource Identifier\)를 나타낸다고 가정합니다.  URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다.  메서드가 URI의 문자열 표현을 사용하면 <xref:System.Uri> 클래스의 인스턴스를 사용하는 해당 오버로드를 제공해야 합니다. 이렇게 하면 서비스가 안전한 방식으로 제공됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 매개 변수를 <xref:System.Uri> 형식으로 변경합니다. 이것이 주요 변경에 해당합니다.  또는 <xref:System.Uri> 매개 변수를 사용하는 메서드의 오버로드를 제공합니다. 이는 주요 변경에 해당하지 않습니다.  
  
## 경고를 표시하지 않는 경우  
 매개 변수가 URI를 나타내지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 `ErrorProne` 형식과 이 규칙을 만족하는 `SaferWay` 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]  
  
## 관련 규칙  
 [CA1056: URI 속성은 문자열이면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)  
  
 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../Topic/CA2234:%20Pass%20System.Uri%20objects%20instead%20of%20strings.md)  
  
 [CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)