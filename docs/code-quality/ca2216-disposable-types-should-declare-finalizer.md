---
title: "CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다. | Microsoft Docs"
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
  - "DisposableTypesShouldDeclareFinalizer"
  - "CA2216"
helpviewer_keywords: 
  - "CA2216"
  - "DisposableTypesShouldDeclareFinalizer"
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DisposableTypesShouldDeclareFinalizer|  
|CheckId|CA2216|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.IDisposable?displayProperty=fullName>을 구현하고, 관리되지 않는 리소스의 사용을 암시하는 필드를 포함하는 형식이 <xref:System.Object.Finalize%2A?displayProperty=fullName>에 설명된 종료자를 구현하지 않습니다.  
  
## 규칙 설명  
 삭제 가능한 형식에 다음 형식의 필드가 포함된 경우 이 규칙 위반이 보고됩니다.  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 해당 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하는 종료자를 구현합니다.  
  
## 경고를 표시하지 않는 경우  
 형식이 관리되지 않는 리소스를 해제할 목적으로 <xref:System.IDisposable>을 구현하지 않는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]  
  
## 관련 규칙  
 [CA2115: 네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.](../Topic/CA2115:%20Call%20GC.KeepAlive%20when%20using%20native%20resources.md)  
  
 [CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)  
  
 [CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)  
  
## 참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)