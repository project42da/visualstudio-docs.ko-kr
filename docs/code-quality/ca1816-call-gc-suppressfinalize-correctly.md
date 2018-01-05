---
title: "CA1816: GC를 호출 합니다. SuppressFinalize 올바르게 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8d0287b570ed1ff5393ff0ff04b9e5d2252c29bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.
|||  
|-|-|  
|TypeName|CallGCSuppressFinalizeCorrectly|  
|CheckId|CA1816|  
|범주|Microsoft 합니다. 사용법|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
  
-   구현 되는 메서드를 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 호출 하지 않습니다 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
-   구현 하지 않은 방법을 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 호출 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
-   메서드 호출 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 이 (Visual Basic의 Me) 이외의 값을 전달 하 고 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드 개체가 가비지 수집을 사용할 수 있게 되기 전에 언제 든 지 리소스를 해제할 수 있습니다. 경우는 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드가 호출 되 면 개체의 리소스를 해제 합니다. 따라서 반드시 종료할 필요가 있습니다. <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>호출 해야 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 하므로 가비지 수집기는 개체의 종료자를 호출 하지 않습니다.  
  
 파생된 형식과 종료자를 다시 구현 하지 않도록 하려면 <xref:System.IDisposable> 계속 호출 해야 unsealed 형식의 종료 자가 없는 호출할 수 및 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면:  
  
 메서드는의 구현 하는 경우 <xref:System.IDisposable.Dispose%2A>, 호출을 추가 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
 메서드 구현의 없으면 <xref:System.IDisposable.Dispose%2A>에 대 한 호출을 제거 하거나 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 형식의를 이동 또는 <xref:System.IDisposable.Dispose%2A> 구현 합니다.  
  
 변경에 대 한 모든 호출 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 이 (Visual Basic의 Me)를 전달할 수 있습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 사용 하 여 의도적는 경우에이 규칙에서 경고를 표시 하지 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 다른 개체의 수명을 제어 합니다. 구현이이 규칙에서는 경고를에서 표시 해야 <xref:System.IDisposable.Dispose%2A> 호출 하지 않습니다 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다. 이런이 경우에 종료 하지 않는 실패 하 고 성능이 저하 됩니다 있으며 이점도 없습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 메서드를 잘못 표시 호출 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]  
  
## <a name="example"></a>예  
 다음 예제에서는 메서드를 보여 줍니다를 올바르게 호출 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>합니다.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
## <a name="see-also"></a>참고 항목  
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)