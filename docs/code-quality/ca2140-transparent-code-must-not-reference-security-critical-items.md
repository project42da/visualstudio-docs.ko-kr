---
title: "CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2129"
  - "SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode"
  - "CA2140"
helpviewer_keywords: 
  - "CA2129"
  - "CA2140"
  - "SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode"
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|  
|CheckId|CA2140|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 투명 메서드:  
  
-   보안에 중요한 보안 예외 형식을 처리합니다.  
  
-   보안에 중요한 형식으로 표시된 매개 변수가 있습니다.  
  
-   보안에 중요한 제약 조건이 있는 제네릭 매개 변수가 있습니다.  
  
-   보안에 중요한 형식의 지역 변수가 있습니다.  
  
-   보안에 중요한 것으로 표시된 형식을 참조합니다.  
  
-   보안에 중요한 것으로 표시된 메서드 호출  
  
-   보안에 중요한 것으로 표시된 필드를 참조합니다.  
  
-   보안에 중요한 것으로 표시된 형식을 반환합니다.  
  
## 규칙 설명  
 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시된 코드 요소는 보안에 중요합니다.  투명 메서드는 보안에 중요한 요소를 사용할 수 없습니다.  투명 형식이 보안에 중요한 형식을 사용하려고 시도하는 경우 <xref:System.TypeAccessException>, <xref:System.MethodAccessException> 또는 <xref:System.FieldAccessException>이 발생합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙의 위반 문제를 해결하려면 다음 중 하나를 실행하십시오.  
  
-   보안에 중요한 코드를 사용하는 코드 요소를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시합니다.  
  
     \- 또는 \-  
  
-   보안에 중요한 것으로 표시된 코드 요소에서 <xref:System.Security.SecurityCriticalAttribute> 특성을 제거하고 <xref:System.Security.SecuritySafeCriticalAttribute> 또는 <xref:System.Security.SecurityTransparentAttribute> 특성으로 표시합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 투명 메서드는 보안에 중요한 제네릭 컬렉션, 보안 중요 필드 및 보안 중요 메서드를 참조하려고 시도합니다.  
  
 [!code-cs[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]  
  
## 참고 항목  
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityCriticalAttribute>   
 <xref:System.Security.SecurityTransparentAttribute>   
 <xref:System.Security.SecurityTreatAsSafeAttribute>   
 <xref:System.Security?displayProperty=fullName>