---
title: "CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2117"
  - "AptcaTypesShouldOnlyExtendAptcaBaseTypes"
helpviewer_keywords: 
  - "AptcaTypesShouldOnlyExtendAptcaBaseTypes"
  - "CA2117"
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|  
|CheckId|CA2117|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 특성이 있는 어셈블리의 public 또는 protected 형식이 해당 특성이 없는 어셈블리에 선언되어 있는 형식으로부터 상속됩니다.  
  
## 규칙 설명  
 기본적으로 강력한 이름이 있는 어셈블리의 public 또는 protected 형식은 완전 신뢰에 대한 [Inheritance Demands](http://msdn.microsoft.com/ko-kr/28b9adbb-8f08-4f10-b856-dbf59eb932d9)에 의해 암시적으로 보호됩니다.  APTCA\(<xref:System.Security.AllowPartiallyTrustedCallersAttribute>\) 특성으로 표시된 강력한 이름의 어셈블리에는 이러한 보호 기능이 없습니다.  이 특성을 사용하면 상속 요청이 사용되지 않습니다.  이렇게 되면 어셈블리에 선언된 노출된 형식이 완전 신뢰가 없는 형식에서 상속될 수 있습니다.  
  
 완전 신뢰 어셈블리에 APTCA 특성이 있고 어셈블리의 형식이 부분 신뢰 호출자를 허용하지 않는 형식에서 상속되면 보안상 위험할 수 있습니다.  두 형식 `T1`과 `T2`가 다음 조건을 충족하면 악의적인 호출자가 `T1` 형식을 사용하여 `T2`를 보호하는 암시적인 완전 신뢰 상속 요청을 건너뛸 수 있습니다.  
  
-   `T1`이 APTCA 특성을 가진 완전 신뢰 어셈블리에 선언된 public 형식입니다.  
  
-   `T1`이 해당 어셈블리 외부에 있는 `T2` 형식에서 상속됩니다.  
  
-   `T2`의 어셈블리에 APTCA 특성이 없으므로 부분 신뢰 어셈블리의 형식에서 상속될 수 없습니다.  
  
 부분 신뢰 형식 `X`는 `T1`에서 상속될 수 있으므로 `T2`에 선언된 상속 멤버에 액세스할 수 있습니다.  `T2`에 APTCA 특성이 없으므로 직접 파생된 형식\(`T1`\)이 완전 신뢰에 대한 상속 요청을 충족해야 합니다. 여기서는 `T1`에 완전 신뢰 권한이 있으므로 이 검사가 충족됩니다.  그러나 `X`는 신뢰할 수 없는 서브클래싱으로부터 `T2`를 보호하는 상속 요청을 만족하지 않으므로 보안상 위험할 수 있습니다.  이러한 이유로 APTCA 특성이 있는 형식은 이 특성이 없는 형식을 확장하면 안 됩니다.  
  
 이보다 더 자주 발생할 수 있는 다른 보안 문제는 파생 형식\(`T1`\)이 프로그래머의 실수로 인해 완전 신뢰가 필요한 형식\(`T2`\)에서 protected 멤버를 노출하는 것입니다.  이러한 문제가 발생하면 신뢰할 수 없는 호출자가 완전 신뢰 형식에서만 사용하도록 해야 하는 정보에 액세스할 수 있게 됩니다.  
  
## 위반 문제를 해결하는 방법  
 위반이 보고된 형식이 APTCA 특성이 필요 없는 어셈블리에 있으면 이 특성을 제거합니다.  
  
 APTCA 특성이 필요하면 해당 형식에 완전 신뢰에 대한 상속 요청을 추가합니다.  그러면 신뢰할 수 없는 형식에 상속되는 것을 막을 수 있습니다.  
  
 위반이 보고된 기본 형식의 어셈블리에 APTCA 특성을 추가하여 위반 문제를 해결할 수 있습니다.  어셈블리의 모든 코드 및 해당 어셈블리에 종속된 모든 코드의 보안 문제를 충분히 검토한 후 이 작업을 수행해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 안전하게 표시하지 않으려면 해당 형식에서 노출한 protected 멤버를 통해 신뢰할 수 없는 호출자가 악용될 가능성이 있는 중요한 정보, 작업 또는 리소스에 직접 또는 간접적으로 액세스하지 못하도록 해야 합니다.  
  
## 예제  
 다음 예제에서는 두 개의 어셈블리와 테스트 응용 프로그램을 사용하여 이 규칙을 통해 감지되는 보안 문제를 보여 줍니다.  첫 번째 어셈블리에는 APTCA 특성이 없으므로 부분 신뢰 형식에서 이를 상속하면 안 됩니다\(이전 설명의 `T2`\).  
  
 [!code-cs[FxCop.Security.NoAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_1.cs)]  
  
## 예제  
 두 번째 어셈블리는 완전 신뢰되므로 부분 신뢰 호출자를 허용합니다\(이전 설명의 `T1`\).  
  
 [!code-cs[FxCop.Security.YesAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_2.cs)]  
  
## 예제  
 테스트 형식\(이전 설명의 `X`\)은 부분 신뢰 어셈블리에 있습니다.  
  
 [!code-cs[FxCop.Security.TestAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_3.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **그늘진 협곡에서 2003년 2월 22일 오전 12시에 만나십시오\!**  
**시작 테스트: sunny meadow**  
**화창한 목초지에서 2003년 2월 22일 오전 12시에 만나십시오\!**   
## 관련 규칙  
 [CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.](../Topic/CA2116:%20APTCA%20methods%20should%20only%20call%20APTCA%20methods.md)  
  
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [.NET Framework Assemblies Callable by Partially Trusted Code](http://msdn.microsoft.com/ko-kr/a417fcd4-d3ca-4884-a308-3a1a080eac8d)   
 [부분 신뢰 코드에서 라이브러리 사용](../Topic/Using%20Libraries%20from%20Partially%20Trusted%20Code.md)   
 [Inheritance Demands](http://msdn.microsoft.com/ko-kr/28b9adbb-8f08-4f10-b856-dbf59eb932d9)