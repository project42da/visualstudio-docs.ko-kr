---
title: "CA2213: 삭제 가능한 필드는 삭제해야 합니다. | Microsoft Docs"
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
  - "DisposableFieldsShouldBeDisposed"
  - "CA2213"
helpviewer_keywords: 
  - "CA2213"
  - "DisposableFieldsShouldBeDisposed"
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2213: 삭제 가능한 필드는 삭제해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DisposableFieldsShouldBeDisposed|  
|CheckId|CA2213|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.IDisposable?displayProperty=fullName>을 구현하는 형식이 마찬가지로 <xref:System.IDisposable>을 구현하는 형식으로 된 필드를 선언합니다.  필드의 <xref:System.IDisposable.Dispose%2A> 메서드가 선언 형식의 <xref:System.IDisposable.Dispose%2A> 메서드에서 호출되지 않습니다.  
  
## 규칙 설명  
 형식에서는 해당 형식의 관리되지 않는 모든 리소스를 삭제해야 하며 <xref:System.IDisposable>을 구현하여 이 작업을 수행합니다.  이 규칙에서는 삭제 가능한 형식 `T`가 삭제 가능한 형식 `FT`의 인스턴스인 `F` 필드를 선언하는지 여부를 확인합니다.  이 규칙에서는 각 `F` 필드에 대해 `FT.Dispose` 호출을 찾습니다.  그런 다음 `T.Dispose`에서 호출하는 메서드와 한 수준 낮은 메서드, 즉 `FT.Dispose`에서 호출하는 메서드에서 호출하는 메서드를 검색합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 필드에서 보유하는 관리되지 않는 리소스를 할당하고 해제할 책임이 있는 경우 <xref:System.IDisposable>을 구현하는 형식의 필드에 대해 <xref:System.IDisposable.Dispose%2A>를 호출합니다.  
  
## 경고를 표시하지 않는 경우  
 필드에서 보유하고 있는 리소스를 해제할 책임이 없거나 <xref:System.IDisposable.Dispose%2A> 호출이 규칙에서 확인하는 호출 수준보다 깊은 호출 수준에서 발생하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IDisposable>을 구현하는 `TypeA` 형식을 보여 줍니다\(이전 설명의 `FT`\).  
  
 [!CODE [FxCop.Usage.IDisposablePattern#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern#1)]  
  
## 예제  
 다음 예제에서는`aFieldOfADisposableType` 필드\(이전 설명의 `F`\)를 삭제 가능한 형식\(`TypeA`\)으로 선언하고 필드에 대해 <xref:System.IDisposable.Dispose%2A>를 호출하지 않음으로써 이 규칙을 위반하는 `TypeB` 형식을 보여 줍니다.  `TypeB`는 이전 토론에서 `T`에 해당합니다.  
  
 [!code-cs[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]  
  
## 참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)