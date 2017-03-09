---
title: "CA2108: 값 형식에서 선언적 보안을 검토하십시오. | Microsoft Docs"
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
  - "ReviewDeclarativeSecurityOnValueTypes"
  - "CA2108"
helpviewer_keywords: 
  - "CA2108"
  - "ReviewDeclarativeSecurityOnValueTypes"
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2108: 값 형식에서 선언적 보안을 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewDeclarativeSecurityOnValueTypes|  
|CheckId|CA2108|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 또는 protected 값 형식이 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md) 또는 [링크 요청](../Topic/Link%20Demands.md)에 의해 보안됩니다.  
  
## 규칙 설명  
 값 형식은 다른 생성자가 실행되기 전에 해당 기본 생성자에서 할당하고 초기화합니다.  값 형식이 Demand 또는 LinkDemand에 의해 보안되고 호출자에게 보안 검사를 만족하는 권한이 없으면 기본 생성자 이외의 모든 생성자가 실패하고 보안 예외가 throw됩니다.  값 형식은 할당 취소되지 않고 기본 생성자에서 설정한 상태로 유지됩니다.  값 형식의 인스턴스를 전달하는 호출자에게 인스턴스를 만들거나 인스턴스에 액세스할 수 있는 권한이 있으리라고 가정하지 마십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식에서 보안 검사를 제거하고 대신 메서드 수준의 보안 검사를 사용해야 합니다.  이러한 방식으로 위반 문제를 해결해도 적합하지 않은 권한을 갖는 호출자가 값 형식의 인스턴스를 얻는 것을 막을 수는 없습니다.  기본 상태에서 값 형식의 인스턴스가 중요한 정보를 노출하지 않는지, 그리고 악용될 소지가 없는지 확인해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 모든 호출자가 보안에 위협을 가하지 않고 기본 상태에서 값 형식의 인스턴스를 얻을 수 있으면 이 규칙에서 경고를 표시하지 않을 수 있습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 값 형식이 들어 있는 라이브러리를 보여 줍니다.  `StructureManager` 형식에서는 값 형식의 인스턴스를 전달하는 호출자가 인스턴스를 만들고 인스턴스에 액세스할 수 있는 권한이 있다고 가정합니다.  
  
 [!code-cs[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 라이브러리의 약점을 보여 줍니다.  
  
 [!code-cs[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **구조체 사용자 지정 생성자: 요청에 실패했습니다.**  
**새 값 SecuredTypeStructure 100 100**  
**새 값 SecuredTypeStructure 200 200**   
## 참고 항목  
 [링크 요청](../Topic/Link%20Demands.md)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)