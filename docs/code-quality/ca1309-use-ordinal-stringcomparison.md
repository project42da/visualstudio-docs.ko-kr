---
title: "CA1309: 서수 StringComparison을 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UseOrdinalStringComparison"
  - "CA1309"
helpviewer_keywords: 
  - "UseOrdinalStringComparison"
  - "CA1309"
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# CA1309: 서수 StringComparison을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseOrdinalStringComparison|  
|CheckId|CA1309|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 비언어 문자열 비교 작업에서는 <xref:System.StringComparison> 매개 변수를 **Ordinal** 또는 **OrdinalIgnoreCase**로 설정하지 않습니다.  
  
## 규칙 설명  
 대부분의 문자열 작업, 특히 <xref:System.String.Compare%2A?displayProperty=fullName> 및 <xref:System.String.Equals%2A?displayProperty=fullName> 메서드가 이제 <xref:System.StringComparision?displayProperty=fullName> 열거형 값을 매개 변수로 사용할 수 있는 오버로드를 제공합니다.  
  
 **StringComparison.Ordinal** 또는 **StringComparison.OrdinalIgnoreCase**를 지정하면 문자열 비교는 비언어 작업이 됩니다.  즉, 비교 작업을 결정할 때 자연 언어와 관련된 기능은 무시됩니다.  따라서 결정 과정에서는 단순한 바이트 비교를 기준으로 사용하고 문화권별로 매개 변수화되는 대\/소문자 또는 같음 테이블은 무시합니다.  결과적으로 매개 변수가 명시적으로 **StringComparison.Ordinal** 또는 **StringComparison.OrdinalIgnoreCase**로 설정되기 때문에 코드 실행 속도, 정확도 및 신뢰도가 향상됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반을 해결하려면 <xref:System.StringComparison?displayProperty=fullName> 열거형을 매개 변수로 사용할 수 있는 오버로드로 문자열 비교 메서드를 변경하고 **Ordinal** 또는 **OrdinalIgnoreCase**를 지정합니다.  예를 들어, `String.Compare(str1, str2)`를 `String.Compare(str1, str2, StringComparison.Ordinal)`로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 라이브러리 또는 응용 프로그램을 제한적인 로컬 사용자에게만 제공하거나 현재 문화권의 의미를 사용해야 하는 경우에는 이 규칙에서 경고를 표시하지 않는 것이 안전합니다.  
  
## 참고 항목  
 [전역화 경고](../code-quality/globalization-warnings.md)   
 [CA1307: StringComparison 지정](../code-quality/ca1307-specify-stringcomparison.md)