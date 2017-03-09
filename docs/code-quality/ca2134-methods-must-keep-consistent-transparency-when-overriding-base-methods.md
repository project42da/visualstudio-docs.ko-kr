---
title: "CA2134: 메서드는 기본 메서드를 재정의할 때 일관성 있는 방식을 유지해야 합니다. | Microsoft Docs"
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
  - "CA2134"
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2134: 메서드는 기본 메서드를 재정의할 때 일관성 있는 방식을 유지해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MethodsMustOverrideWithConsistentTransparency|  
|CheckId|CA2134|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 이 규칙은 <xref:System.Security.SecurityCriticalAttribute>로 표시된 메서드가 투명하거나 <xref:System.Security.SecuritySafeCriticalAttribute>로 표시된 메서드를 재정의할 때 실행됩니다.  또한 규칙은 투명하거나 <xref:System.Security.SecuritySafeCriticalAttribute>로 표시된 메서드가 <xref:System.Security.SecurityCriticalAttribute>로 표시된 메서드를 재정의할 때 실행됩니다.  
  
 이 규칙은 가상 메서드를 재정의하거나 인터페이스를 구현할 때 적용됩니다.  
  
## 규칙 설명  
 이 규칙은 상속 체인으로 메서드의 보안 액세스 가능성을 변경하려는 시도가 있을 때 실행됩니다.  예를 들어, 기본 클래스의 가상 메서드가 투명 또는 안전한 중요한 경우 파생된 클래스는 투명 또는 안전에 중요한 메서드로 재정의해야 합니다.  반대로, 가상 보안이 중요한 경우 파생된 클래스는 보안 중요 메서드로 재정의해야 합니다.  인터페이스 메서드를 구현하는 데 동일한 규칙이 적용됩니다.  
  
 코드가 런타임 대신 JIT 컴파일될 때 투명성 규칙이 적용되므로 투명도 계산은 동적 형식 정보를 갖지 않습니다.  따라서 투명도 계산의 결과는 동적 형식에 관계 없이 JIT 컴파일되는 정적 형식에서만 확인할 수 있어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙의 위반 문제를 해결하려면 가상 메서드를 재정의하거나 인터페이스를 구현하는 메서드의 투명성을 가상 또는 인터페이스 메서드의 투명도에 일치하도록 변경하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  이 규칙 위반은 수준 2 투명성을 사용하는 어셈블리에 대해 런타임 <xref:System.TypeLoadException>에서 발생합니다.  
  
## 예제  
  
### 코드  
 [!code-cs[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]  
  
## 참고 항목  
 [보안 투명 코드, 수준 2](../Topic/Security-Transparent%20Code,%20Level%202.md)