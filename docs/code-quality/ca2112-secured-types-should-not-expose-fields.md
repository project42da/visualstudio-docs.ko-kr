---
title: "CA2112: 보안 형식은 필드를 노출하면 안 됩니다. | Microsoft Docs"
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
  - "CA2112"
  - "SecuredTypesShouldNotExposeFields"
helpviewer_keywords: 
  - "CA2112"
  - "SecuredTypesShouldNotExposeFields"
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2112: 보안 형식은 필드를 노출하면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SecuredTypesShouldNotExposeFields|  
|CheckId|CA2112|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 public 필드를 포함하고 [링크 요청](../Topic/Link%20Demands.md)에 의해 보안됩니다.  
  
## 규칙 설명  
 코드에 링크 요청으로 보안된 형식의 인스턴스에 대한 액세스 권한이 있으면 코드에서 링크 요청을 만족하지 않아도 해당 형식의 필드에 액세스할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 필드를 public이 아닌 필드로 만들고 필드 데이터를 반환하는 public 속성 또는 메서드를 추가합니다.  형식에 대한 LinkDemand 보안 검사는 형식의 속성 및 메서드에 대한 액세스를 보호합니다.  그러나 코드 액세스 보안이 필드에는 적용되지 않습니다.  
  
## 경고를 표시하지 않는 경우  
 보안 문제를 해결하고 디자인을 향상시키려면 public 필드를 public이 아닌 필드로 만들어 위반 문제를 해결해야 합니다.  필드에 보안을 유지해야 하는 정보가 들어 있지 않고 필드의 내용에 의존하지 않는 경우에는 이 규칙에서 경고를 표시하지 않을 수 있습니다.  
  
## 예제  
 다음 예제에서는 보안되지 않는 필드가 있는 라이브러리 형식\(`SecuredTypeWithFields`\)을 보여 주고, 이 라이브러리 형식의 인스턴스를 만들 수 있는 형식\(`Distributor`\)과 이를 만들 권한이 없는 형식에 인스턴스를 잘못 전달하는 동작을 보여 주며, 형식에 대한 보안 권한이 없는 경우에도 인스턴스의 필드를 읽을 수 있는 응용 프로그램 코드를 보여 줍니다.  
  
 다음 라이브러리 코드는 규칙을 위반합니다.  
  
 [!code-cs[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]  
  
## 예제  
 보안 형식을 보호하는 링크 요청 때문에 응용 프로그램에서 인스턴스를 만들 수 없습니다.  응용 프로그램에서는 다음 클래스를 사용하여 보안 형식의 인스턴스를 가져올 수 있습니다.  
  
 [!code-cs[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 보안 형식의 메서드에 대한 액세스 권한 없이 코드에서 해당 필드에 액세스할 수 있는 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **SecuredTypeWithFields 인스턴스를 만들고 있습니다.**  
**Secured 형식 필드: 22, 33**  
**보안된 형식의 필드를 변경하는 중...**  
**캐시된 개체 필드: 99, 33**   
## 관련 규칙  
 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## 참고 항목  
 [링크 요청](../Topic/Link%20Demands.md)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)