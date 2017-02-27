---
title: "CA1307: StringComparison 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1307"
  - "SpecifyStringComparison"
helpviewer_keywords: 
  - "CA1307"
  - "SpecifyStringComparison"
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 11
---
# CA1307: StringComparison 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SpecifyStringComparison|  
|CheckId|CA1307|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 문자열 비교 작업에서 <xref:System.StringComparison> 매개 변수를 설정하지 않는 메서드 오버로드를 사용합니다.  
  
## 규칙 설명  
 대부분의 문자열 작업, 특히 <xref:System.String.Compare%2A> 및 <xref:System.String.Equals%2A> 메서드가 <xref:System.StringComparison> 열거형 값을 매개 변수로 사용할 수 있는 오버로드를 제공합니다.  
  
 <xref:System.StringComparison> 매개 변수를 사용하는 오버로드가 있는 경우에는 항상 이 매개 변수를 사용하지 않는 오버로드 대신 이 오버로드를 사용해야 합니다.  이 매개 변수를 명시적으로 설정하면 코드가 보다 명확해지고 유지 관리하기가 쉬워집니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙의 위반을 해결하려면 <xref:System.StringComparison> 열거형을 매개 변수로 사용할 수 있는 오버로드로 문자열 비교 메서드를 변경합니다.  예를 들어 `String.Compare(str1, str2)`를 `String.Compare(str1, str2, StringComparison.Ordinal)`로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 라이브러리 또는 응용 프로그램을 제한적인 로컬 사용자에게만 제공하므로 지역화할 필요가 없는 경우에는 이 규칙에서 경고를 표시하지 않는 것이 안전합니다.  
  
## 참고 항목  
 [전역화 경고](../code-quality/globalization-warnings.md)   
 [CA1309: 서수 StringComparison을 사용하십시오.](../code-quality/ca1309-use-ordinal-stringcomparison.md)