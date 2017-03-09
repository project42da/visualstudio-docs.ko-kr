---
title: "CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다. | Microsoft Docs"
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
  - "AvoidInt64ArgumentsForVB6Clients"
  - "CA1406"
helpviewer_keywords: 
  - "AvoidInt64ArgumentsForVB6Clients"
  - "CA1406"
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidInt64ArgumentsForVB6Clients|  
|CheckId|CA1406|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 COM\(Component Object Model\)에서 볼 수 있는 것으로 표시된 형식이 <xref:System.Int64?displayProperty=fullName> 인수를 사용하는 멤버를 선언합니다.  
  
## 규칙 설명  
 Visual Basic 6 COM 클라이언트는 64비트 정수에 액세스할 수 없습니다.  
  
 기본적으로 어셈블리, public 형식, public 형식의 public 인스턴스 멤버, public 값 형식의 모든 멤버는 COM에서 볼 수 있습니다.  하지만 가양성\(false positives\)을 줄이기 위해 이 규칙에서는 형식의 COM 노출 여부를 명시적으로 지정하도록 요구합니다. 포함 어셈블리는 `false`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>로 표시되어야 하며 형식은 `true`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute>로 표시되어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 값을 항상 32비트 정수 계열로 표현할 수 있는 매개 변수의 경우 이 규칙 위반 문제를 해결하려면 매개 변수 형식을 <xref:System.Int32?displayProperty=fullName>로 변경합니다.  매개 변수의 값이 32비트 정수 계열로 표현할 수 있는 것보다 큰 경우에는 매개 변수 형식을 <xref:System.Decimal?displayProperty=fullName>로 변경합니다.  <xref:System.Single?displayProperty=fullName>과 <xref:System.Double?displayProperty=fullName> 모두 <xref:System.Int64> 데이터 형식의 상위 범위에서 정밀도가 떨어집니다.  멤버를 COM에서 볼 수 없도록 하려면 해당 멤버를 `false`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute>로 표시합니다.  
  
## 경고를 표시하지 않는 경우  
 Visual Basic 6 COM 클라이언트가 해당 형식에 액세스하지 않는 것이 확실한 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]  
  
## 관련 규칙  
 [CA1413: ComVisible 값 형식에 public이 아닌 필드를 사용하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
 [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](../Topic/CA1407:%20Avoid%20static%20members%20in%20COM%20visible%20types.md)  
  
 [CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Long Data Type](/dotnet/visual-basic/language-reference/data-types/long-data-type)