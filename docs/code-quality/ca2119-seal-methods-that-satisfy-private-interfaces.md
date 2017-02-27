---
title: "CA2119: private 인터페이스를 만족하는 메서드를 봉인하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SealMethodsThatSatisfyPrivateInterfaces"
  - "CA2119"
helpviewer_keywords: 
  - "CA2119"
  - "SealMethodsThatSatisfyPrivateInterfaces"
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA2119: private 인터페이스를 만족하는 메서드를 봉인하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|  
|CheckId|CA2119|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 상속할 수 있는 public 형식에서 `internal`\(Visual Basic의 경우 `Friend`\) 인터페이스의 재정의 가능한 메서드 구현을 제공합니다.  
  
## 규칙 설명  
 인터페이스 메서드에는 구현 형식에 따라 변경될 수 없는 공용 액세스 가능성이 있습니다.  내부 인터페이스는 인터페이스를 정의하는 어셈블리 외부에서 구현되지 않도록 하는 계약을 만듭니다.  `virtual`\(Visual Basic의 경우 `Overridable`\) 한정자를 사용하여 내부 인터페이스의 메서드를 구현하는 public 형식을 사용하면 어셈블리 외부에 있는 파생된 형식으로 메서드를 재정의할 수 있습니다.  정의 어셈블리의 두 번째 형식에서 메서드를 호출하고 내부 전용 계약이 반환되어야 하는 경우 외부 어셈블리에서 재정의된 메서드가 실행되면 동작이 잘못 수행될 수 있습니다.  이 경우 보안 문제가 생길 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드가 어셈블리 외부에서 재정의되지 않도록 다음 방법 중 하나를 사용합니다.  
  
-   선언 형식을 `sealed`\(Visual Basic의 경우 `NotInheritable`\)로 만듭니다.  
  
-   선언 형식의 액세스 가능성을 `internal`\(Visual Basic의 경우 `Friend`\)로 변경합니다.  
  
-   선언 형식에서 모든 public 생성자를 제거합니다.  
  
-   `virtual` 한정자를 사용하지 않고 메서드를 구현합니다.  
  
-   메서드를 명시적으로 구현합니다.  
  
## 경고를 표시하지 않는 경우  
 신중하게 검토하여 메서드가 어셈블리 외부에서 재정의되더라도 보안 문제가 발생하지 않을 것이라고 확신하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식 `BaseImplementation`을 보여 줍니다.  
  
 [!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
 [!code-cs[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
 [!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]  
  
## 예제  
 다음 예제에서는 이전 예제의 가상 메서드 구현을 악용하는 경우를 보여 줍니다.  
  
 [!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
 [!code-cs[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
 [!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]  
  
## 참고 항목  
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)   
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)