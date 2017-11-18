---
title: "CA2243: 특성 문자열 리터럴이 올바르게 구문 분석 되어야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3ec86725873f5724609f411072dab4a4bde9d990
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.
|||  
|-|-|  
|TypeName|AttributeStringLiteralsShouldParseCorrectly|  
|CheckId|CA2243|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 특성의 문자열 리터럴 매개 변수가 URL, GUID 또는 버전에 대 한 올바르게 구문 분석 하지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 특성에서 파생 된 이후 <xref:System.Attribute?displayProperty=fullName>, 컴파일 타임에 특성을 사용 하 고, 상수 값만 생성자를 전달할 수 있습니다. Url, Guid 및 버전을 나타내야 하는 특성 매개 변수로 형식화 될 수 없습니다 <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, 및 <xref:System.Version?displayProperty=fullName>이러한 형식을 상수로 표현할 수 없기 때문에, 합니다. 대신, 문자열로 표현 되어야 합니다.  
  
 없기 때문에 매개 변수는 string으로 형식화 되어, 컴파일 타임에는 잘못 된 형식의 매개 변수를 전달할 수 있습니다.  
  
 이 규칙 uniform resource identifier (URI), 전역적으로 고유 식별자 (GUID) 또는 버전을 나타내는 매개 변수를 찾으려면 명명 추론을 사용 하 고 전달 된 값이 올바른지 확인 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 매개 변수 문자열 올바른 형식의 URL, GUID 또는 버전을 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 매개 변수가 URL, GUID 또는 버전 나타내지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는이 규칙을 위반 하는 AssemblyFileVersionAttribute에 대 한 코드를 보여 줍니다.  
  
 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]  
  
 규칙은 다음에 의해 트리거됩니다.  
  
-   System.Version을 구문 분석할 수 없습니다 및 'version'를 포함 하는 매개 변수입니다.  
  
-   System.Guid를 구문 분석할 수 없습니다 및 'guid'를 포함 하는 매개 변수입니다.  
  
-   형식을 System.Uri로 구문 분석할 수 없습니다. 'uri', 'urn' 또는 'url'를 포함 하는 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)