---
title: "CA1413: ComVisible 값 형식에 public이 아닌 필드를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1413"
  - "AvoidNonpublicFieldsInComVisibleValueTypes"
helpviewer_keywords: 
  - "CA1413"
  - "AvoidNonpublicFieldsInComVisibleValueTypes"
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1413: ComVisible 값 형식에 public이 아닌 필드를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|  
|CheckId|CA1413|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 COM\(Component Object Model\)에 노출되도록 특별히 표시된 값 형식이 public이 아닌 인스턴스 필드를 선언합니다.  
  
## 규칙 설명  
 public이 아니며 값 형식이 COM에 노출되는 인스턴스 필드는 COM 클라이언트에서 볼 수 있습니다.  필드의 내용을 검토하여 노출되지 않아야 하거나 디자인 또는 보안에 의도하지 않은 영향을 줄 수 있는 정보가 있는지 확인합니다.  
  
 기본적으로 모든 public 값 형식은 COM에서 볼 수 있습니다.  그러나 가양성을 줄이기 위해 이 규칙은 COM 표시 유형을 명시적으로 언급할 것을 요구합니다.  포함하는 어셈블리는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>을 `false`로 설정된 상태로 표시해야 하며 형식은 <xref:System.Runtime.InteropServices.ComVisibleAttribute>을 `true`로 설정한 상태로 표시합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하고 필드 숨김을 유지하려면 값 형식을 참조 형식으로 변경하거나 형식에서 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성을 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 필드를 노출해도 괜찮은 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]  
  
## 관련 규칙  
 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](../Topic/CA1407:%20Avoid%20static%20members%20in%20COM%20visible%20types.md)  
  
 [CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [상호 운용할 .NET 형식의 정규화](../Topic/Qualifying%20.NET%20Types%20for%20Interoperation.md)