---
title: "CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다. | Microsoft Docs"
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
  - "CA1049"
  - "TypesThatOwnNativeResourcesShouldBeDisposable"
helpviewer_keywords: 
  - "TypesThatOwnNativeResourcesShouldBeDisposable"
  - "CA1049"
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|  
|CheckId|CA1049|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식이 <xref:System.IntPtr?displayProperty=fullName> 필드, <xref:System.UIntPtr?displayProperty=fullName> 필드 또는 <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> 필드를 참조하지만 <xref:System.IDisposable?displayProperty=fullName>을 구현하지 않습니다.  
  
## 규칙 설명  
 이 규칙에서는 <xref:System.IntPtr>, <xref:System.UIntPtr> 및 <xref:System.Runtime.InteropServices.HandleRef> 필드에 관리되지 않는 리소스에 대한 포인터가 저장된다고 가정합니다.  관리되지 않는 리소스를 할당하는 형식은 <xref:System.IDisposable>을 구현하여 호출자가 필요할 때 해당 리소스를 해제할 수 있도록 하고 리소스를 차지하고 있는 개체의 수명을 줄여야 합니다.  
  
 관리되지 않는 리소스를 정리하는 데 권장되는 디자인 패턴은 각각 <xref:System.Object.Finalize%2A?displayProperty=fullName> 메서드와 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드를 사용하여 해당 리소스를 해제하기 위한 암시적 방법과 명시적 방법을 모두 제공하는 것입니다.  가비지 수집기에서는 개체에 더 이상 접근할 수 없음을 확인한 후 아무 때나 개체의 <xref:System.Object.Finalize%2A> 메서드를 호출합니다.  <xref:System.Object.Finalize%2A>가 호출된 후에는 추가적인 가비지 수집을 수행하여 개체를 해제해야 합니다.  <xref:System.IDisposable.Dispose%2A> 메서드를 통해 호출자는 리소스가 가비지 수집기에 남겨져 해제되기 전에 필요에 따라 리소스를 명시적으로 해제할 수 있습니다.  관리되지 않는 리소스를 정리한 후 <xref:System.IDisposable.Dispose%2A>는 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 메서드를 호출하여 가비지 수집기에서 <xref:System.Object.Finalize%2A>를 더 이상 호출할 필요가 없음을 인식하도록 해야 합니다. 이렇게 하면 추가적인 가비지 수집이 필요 없고 개체의 수명이 단축됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.IDisposable>을 구현합니다.  
  
## 경고를 표시하지 않는 경우  
 형식이 관리되지 않는 리소스를 참조하지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  그렇지 않을 경우, <xref:System.IDisposable> 구현에 실패하면 관리되지 않는 리소스를 사용할 수 없게 될 수 있으므로 이 규칙에서 경고를 표시하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.IDisposable>을 구현하여 관리되지 않는 리소스를 정리하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]  
  
## 관련 규칙  
 [CA2115: 네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.](../Topic/CA2115:%20Call%20GC.KeepAlive%20when%20using%20native%20resources.md)  
  
 [CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)  
  
 [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
 [CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.](../Topic/CA1001:%20Types%20that%20own%20disposable%20fields%20should%20be%20disposable.md)  
  
## 참고 항목  
 [Cleaning Up Unmanaged Resources](../Topic/Cleaning%20Up%20Unmanaged%20Resources.md)   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)