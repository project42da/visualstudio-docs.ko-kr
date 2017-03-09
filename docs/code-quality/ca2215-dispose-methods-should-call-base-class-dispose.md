---
title: "CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다. | Microsoft Docs"
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
  - "CA2215"
  - "DisposeMethodsShouldCallBaseClassDispose"
  - "Dispose methods should call base class dispose"
helpviewer_keywords: 
  - "DisposeMethodsShouldCallBaseClassDispose"
  - "CA2215"
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DisposeMethodsShouldCallBaseClassDispose|  
|CheckId|CA2215|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.IDisposable?displayProperty=fullName>을 구현하는 형식이 마찬가지로 <xref:System.IDisposable>을 구현하는 형식에서 상속됩니다.  상속하는 형식의 <xref:System.IDisposable.Dispose%2A> 메서드가 부모 형식의 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하지 않습니다.  
  
## 규칙 설명  
 삭제 가능한 형식에서 상속되는 형식은 자신의 <xref:System.IDisposable.Dispose%2A> 메서드에서 기본 형식의 <xref:System.IDisposable.Dispose%2A> 메서드를 호출해야 합니다.  기본 형식 메서드 Dispose를 호출하면 기본 형식에 의해 만들어진 모든 리소스가 해제되지 않습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 사용자의 <xref:System.IDisposable.Dispose%2A> 메서드에서 `base`.<xref:System.IDisposable.Dispose%2A>를 호출합니다.  
  
## 경고를 표시하지 않는 경우  
 `base`.<xref:System.IDisposable.Dispose%2A> 호출이 규칙에서 검사하는 호출 수준보다 깊은 호출 수준에서 발생할 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IDisposable>을 구현하는 `TypeA` 형식을 보여 줍니다.  
  
 [!CODE [FxCop.Usage.IDisposablePattern#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern#1)]  
  
## 예제  
 다음 예제에서는 `TypeA` 형식에서 상속되고 해당 <xref:System.IDisposable.Dispose%2A> 메서드를 올바로 호출하는 `TypeB` 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_1.vb)]  
  
## 참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)