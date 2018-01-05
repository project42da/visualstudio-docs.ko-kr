---
title: "CA1033: 인터페이스 메서드 자식 형식에서 호출할 수 있어야 합니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a9596a147ab16961d6c1396c0d367f87c6182e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.
|||  
|-|-|  
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|  
|CheckId|CA1033|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 unsealed 형식이 public 인터페이스의 명시적 메서드 구현을 제공하면서 외부에서 볼 수 있는 같은 이름의 대체 메서드를 제공하지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 명시적으로 공용 인터페이스 메서드를 구현 하는 기본 형식인을 것이 좋습니다. 기본 형식에서 파생 되는 형식의 현재 인스턴스에 대 한 참조를 통해서만 상속 된 인터페이스 메서드를 액세스할 수 있습니다 (`this` C#) 인터페이스로 캐스팅 되 합니다. 파생 된 형식 상속 된 인터페이스 메서드를 명시적으로 다시 구현 하는 경우의 기본 구현은 더 이상 액세스할 수 없습니다. 현재 인스턴스 참조를 통해 호출 되며 호출 파생된 구현을 제공 합니다. 그러면, 재귀 및 스택 오버플로가 발생 합니다.  
  
 이 규칙에서는 명시적 구현에 대 한 위반을 보고 하지 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 외부에서 볼 때 `Close()` 또는 `System.IDisposable.Dispose(Boolean)` 메서드가 제공 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 파생된 형식에 표시 되 고 동일한 기능을 노출 하는 새 메서드를 구현 하거나 명시적이 아닌 구현을 변경 합니다. 주요 변경 내용 허용 되는 경우 대신 봉인 형식을 쉽게 것입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 외부에 표시 되는 메서드를 기능은 다른 이름 명시적으로 구현 된 메서드와 같지만 제공할 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 형식 `ViolatingBase`, 규칙을 위반 하는 형식이 있는 `FixedBase`, 위반에 대 한 수정을 보여 주는 합니다.  
  
 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)