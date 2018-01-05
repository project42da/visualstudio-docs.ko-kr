---
title: "CA1049: 네이티브 리소스가 있는 형식은 삭제 가능 해야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d387cd29b0c17bdb31db495fe42146cf1a886d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.
|||  
|-|-|  
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|  
|CheckId|CA1049|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 형식 참조는 <xref:System.IntPtr?displayProperty=fullName> 필드는 <xref:System.UIntPtr?displayProperty=fullName> 필드 또는 <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> 필드 하지만 구현 하지 않는 <xref:System.IDisposable?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙에 있다고 가정 <xref:System.IntPtr>, <xref:System.UIntPtr>, 및 <xref:System.Runtime.InteropServices.HandleRef> 필드는 관리 되지 않는 리소스에 대 한 포인터를 저장 합니다. 관리 되지 않는 리소스를 할당 하는 형식은 구현 <xref:System.IDisposable> 호출자가 필요에 따라 이러한 리소스를 해제 하 고 리소스를 차지 하는 개체의 수명을 줄여야 수 있도록 합니다.  
  
 관리 되지 않는 리소스를 해제 하려면 권장 되는 디자인 패턴은 암시적 및 사용 하 여 이러한 리소스를 해제 수 있는 명시적 방법을 제공 하는 <xref:System.Object.Finalize%2A?displayProperty=fullName> 메서드 및 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드를 각각. 가비지 컬렉션이 <xref:System.Object.Finalize%2A> 개체가 더 이상 접근할 수를 확인 되는 임의의 시점에 개체의 메서드. 후 <xref:System.Object.Finalize%2A> 호출 되는 추가 가비지 수집 개체를 해제 해야 합니다. <xref:System.IDisposable.Dispose%2A> 메서드를 사용 하면 호출자를 명시적으로 가비지 수집기에 남아 있는 경우 리소스 해제 되기 이전의 필요에 따라 리소스를 해제 합니다. 관리 되지 않는 리소스 정리 후 <xref:System.IDisposable.Dispose%2A> 호출 해야는 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 메서드를 가비지 수집기를 것을 알고 <xref:System.Object.Finalize%2A> 를; 호출 하려면가 더 이상 추가 가비지 수집에 대 한 필요성을 제거 하 고 단축이 고 개체의 수명입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 구현 <xref:System.IDisposable>합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 형식이 관리 되지 않는 리소스를 참조 하지 않을 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 때문에이 규칙에서 경고를 표시 하지 마십시오 그렇지 않은 경우를 구현 하지 못하면 <xref:System.IDisposable> 하면 관리 되지 않는 리소스를 사용할 수 없게 될 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 구현 하는 형식을 <xref:System.IDisposable> 관리 되지 않는 리소스를 정리할 수 있습니다.  
  
 [!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2115: 네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)  
  
 [CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)  
  
 [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
 [CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)  
  
## <a name="see-also"></a>참고 항목  
 [관리 되지 않는 리소스 정리](/dotnet/standard/garbage-collection/unmanaged)   
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)