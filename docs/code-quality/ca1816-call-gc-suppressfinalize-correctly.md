---
title: "CA1816: GC.SuppressFinalize를 올바르게 호출하십시오. | Microsoft Docs"
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
  - "CA1816"
  - "DisposeMethodsShouldCallSuppressFinalize"
helpviewer_keywords: 
  - "CA1816"
  - "DisposeMethodsShouldCallSuppressFinalize"
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CallGCSuppressFinalizeCorrectly|  
|CheckId|CA1816|  
|범주|Microsoft.  용도|  
|변경 수준|주요 변경 아님|  
  
## 원인  
  
-   <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>를 구현하는 메서드에서 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출하지 않습니다.  
  
-   <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>를 구현하지 않는 메서드에서 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출합니다.  
  
-   메서드에서 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출하면서 이것\(Visual Basic의 경우 Me\)이 아닌 다른 개체를 전달합니다.  
  
## 규칙 설명  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드를 사용하면 개체가 가비지 수집 대상이 되기 전에 언제든지 리소스를 해제할 수 있습니다.  <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드를 호출하면 개체의 리소스가 해제됩니다.  따라서 반드시 종료할 필요가 없습니다.  <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>에서는 가비지 수집기가 개체의 종료자를 호출하지 않도록 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출해야 합니다.  
  
 종료자가 있는 파생 형식에서 [System.IDisposable](assetId:///System.IDisposable?qualifyHint=True&autoUpgrade=False)을 다시 구현하여 호출할 필요가 없게 하려면 종료자가 없는 봉인되지 않은 형식에서도 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 다음을 수행합니다.  
  
 <xref:System.IDisposable.Dispose%2A>를 구현하는 메서드인 경우 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>에 대한 호출을 추가합니다.  
  
 <xref:System.IDisposable.Dispose%2A>를 구현하는 메서드가 아닌 경우 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>에 대한 호출을 제거하거나 형식의 <xref:System.IDisposable.Dispose%2A> 구현으로 옮깁니다.  
  
 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>에 대한 모든 호출을 이곳으로 전달하도록 변경합니다\(Visual Basic의 경우 Me\).  
  
## 경고를 표시하지 않는 경우  
 의도적으로 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 사용하여 다른 개체의 수명을 제어하는 경우에만 이 규칙에 따른 경고를 표시하지 마십시오.  <xref:System.IDisposable.Dispose%2A>의 구현에서 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 호출하지 않는 경우에는 이 규칙에 따른 경고를 표시해야 합니다.  이러한 경우 종료를 억제하지 않으면 성능이 저하되고 다른 이점도 없습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 올바르지 않게 호출하는 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
 [!code-cs[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>를 올바르게 호출하는 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
 [!code-cs[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]  
  
## 관련 규칙  
 [CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
## 참고 항목  
 [삭제 패턴](../Topic/Dispose%20Pattern.md)