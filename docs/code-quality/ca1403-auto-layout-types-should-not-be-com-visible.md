---
title: "CA1403: 자동 레이아웃 형식은 COM 노출이면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AutoLayoutTypesShouldNotBeComVisible"
  - "CA1403"
helpviewer_keywords: 
  - "CA1403"
  - "AutoLayoutTypesShouldNotBeComVisible"
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1403: 자동 레이아웃 형식은 COM 노출이면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AutoLayoutTypesShouldNotBeComVisible|  
|CheckId|CA1403|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 COM\(Component Object Model\) 노출 형식은 <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=fullName>로 설정한 <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> 특성으로 표시되어 있습니다.  
  
## 규칙 설명  
 <xref:System.Runtime.InteropServices.LayoutKind> 레이아웃 형식은 공용 언어 런타임에 의해 관리됩니다.  이들 형식의 레이아웃은 .NET Framework 버전 간에 변경될 수 있으므로 특정 레이아웃이 필요한 COM 클라이언트에서는 문제가 발생할 수 있습니다.  <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 지정하지 않으면 C\#, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 및 C\+\+ 컴파일러에서는 값 형식에 대해 <xref:System.Runtime.InteropServices.LayoutKind> 레이아웃을 지정합니다.  
  
 따로 표시되지 않은 경우 제네릭이 아닌 모든 public 형식은 COM에서 볼 수 있으며 public이 아닌 모든 제네릭 형식은 COM에서 볼 수 없습니다.  하지만 가양성\(false positives\)을 줄이기 위해 이 규칙에서는 형식의 COM 노출 여부를 명시적으로 지정하도록 요구합니다. 포함 어셈블리는 `false`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>로 표시되어야 하며 형식은 `true`로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute>로 표시되어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성의 값을 <xref:System.Runtime.InteropServices.LayoutKind> 또는 <xref:System.Runtime.InteropServices.LayoutKind>로 변경하거나 형식을 COM에서 볼 수 없도록 만드십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식과 이 규칙을 충족하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]  
  
## 관련 규칙  
 [CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## 참고 항목  
 [Introducing the Class Interface](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [상호 운용할 .NET 형식의 정규화](../Topic/Qualifying%20.NET%20Types%20for%20Interoperation.md)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)