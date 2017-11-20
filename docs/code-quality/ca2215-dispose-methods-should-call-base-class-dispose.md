---
title: "CA2215: Dispose 메서드 기본 클래스 dispose를 호출 해야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0659b9ec82353e3c658f1ba89f07fad197dd8670
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.
|||  
|-|-|  
|TypeName|DisposeMethodsShouldCallBaseClassDispose|  
|CheckId|CA2215|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 구현 하는 형식은 <xref:System.IDisposable?displayProperty=fullName> 도 구현 하는 형식에서 상속 <xref:System.IDisposable>합니다. <xref:System.IDisposable.Dispose%2A> 상속 하는 형식의 메서드를 호출 하지 않습니다는 <xref:System.IDisposable.Dispose%2A> 부모 형식의 메서드.  
  
## <a name="rule-description"></a>규칙 설명  
 삭제 가능한 형식 으로부터 상속 하는 형식, 호출 해야 합니다는 <xref:System.IDisposable.Dispose%2A> 메서드 자체 내에서 기본 형식을 <xref:System.IDisposable.Dispose%2A> 메서드. 기본 형식 메서드를 호출 Dispose 사용 하면 기본 형식에 의해 만들어진 모든 리소스가 해제 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 호출 `base`.<xref:System.IDisposable.Dispose%2A> 에 프로그램 <xref:System.IDisposable.Dispose%2A> 메서드.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 경우이 규칙에서는 경고를에서 표시 하지 않으려면 안전에 대 한 호출 `base`.<xref:System.IDisposable.Dispose%2A> 규칙 검사 보다 깊은 호출 수준에서 발생 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 형식 `TypeA` 를 구현 하는 <xref:System.IDisposable>합니다.  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 형식 `TypeB` 형식에서 상속 되 `TypeA` 올바르게 호출 하 고 해당 <xref:System.IDisposable.Dispose%2A> 메서드.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)