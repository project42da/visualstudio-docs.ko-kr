---
title: "CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다. | Microsoft Docs"
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
  - "CA1405"
  - "ComVisibleTypeBaseTypesShouldBeComVisible"
helpviewer_keywords: 
  - "CA1405"
  - "ComVisibleTypeBaseTypesShouldBeComVisible"
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|  
|CheckId|CA1405|  
|범주|Microsoft.Interoperability|  
|변경 수준|DependsOnFix|  
  
## 원인  
 COM\(Component Object Model\) 노출 형식이 COM에 노출되지 않는 형식에서 파생됩니다.  
  
## 규칙 설명  
 COM 노출 형식이 새 버전에서 멤버를 추가하는 경우 현재 버전에 바인딩된 COM 클라이언트에서 문제가 발생하지 않도록 하려면 엄격한 지침을 따라야 합니다.  COM에서 볼 수 없는 형식은 새 멤버를 추가할 때 이러한 COM 버전 관리 규칙을 따를 필요가 없는 것으로 간주됩니다.  하지만 COM 노출 형식이 COM에서 볼 수 없는 형식에서 파생되고 <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ClassInterfaceType>\(기본값\)의 클래스 인터페이스를 노출하는 경우 기본 형식의 모든 public 멤버\(특별히 COM에서 볼 수 없다고 표시되지 않은 경우\)가 COM에 노출됩니다.  기본 형식이 이후 버전에서 새 멤버를 추가하는 경우 파생된 형식의 클래스 인터페이스에 바인딩된 모든 COM 클라이언트에 문제가 발생할 수 있습니다.  COM 클라이언트에서 문제가 발생할 가능성을 줄이려면 COM 노출 형식이 COM 노출 형식에서만 파생되어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 기본 형식을 COM에서 볼 수 있도록 만들거나 파생된 형식을 COM에서 볼 수 없도록 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-cs[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>   
 [Introducing the Class Interface](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)