---
title: 'CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능 해야 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1306f594af4639d1b2af24d07e4654f8825cd3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.
|||  
|-|-|  
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|  
|CheckId|CA1001|  
|범주|Microsoft.Design|  
|변경 수준|아님-형식이 어셈블리 외부에 표시 되지 않습니다.<br /><br /> 주요 변경-형식이 어셈블리 외부에 표시 되는 경우|  
  
## <a name="cause"></a>원인  
 클래스 선언 하 고는 인스턴스 필드를 구현 하는 <xref:System.IDisposable?displayProperty=fullName> 형식 및 클래스를 구현 하지 않는 <xref:System.IDisposable>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 클래스에서 구현 하는 <xref:System.IDisposable> 인터페이스를 소유 하는 관리 되지 않는 리소스를 삭제 합니다. 인스턴스 필드를 한 <xref:System.IDisposable> 형식 필드 관리 되지 않는 리소스를 소유 하 고 있음을 나타냅니다. 선언 하는 클래스는 <xref:System.IDisposable> 필드에서 간접적으로 관리 되지 않는 리소스를 소유 하 고 구현 해야는 <xref:System.IDisposable> 인터페이스입니다. 클래스는 관리 되지 않는 리소스를 직접 소유 하지 않은, 경우 종료자를 구현 하지 않아야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 구현 <xref:System.IDisposable> 들어오고는 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드 호출에서 <xref:System.IDisposable.Dispose%2A> 필드의 메서드가 있습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 클래스 및 구현 하 여 규칙을 충족 하는 클래스 <xref:System.IDisposable>합니다. 클래스는 직접 관리 되지 않는 리소스를 소유 하지 때문에 클래스 종료자를 구현 하지 않습니다.  
  
 [!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
 [!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
 [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
 [CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)