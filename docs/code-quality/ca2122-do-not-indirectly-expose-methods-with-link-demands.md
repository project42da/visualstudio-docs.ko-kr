---
title: "CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오. | Microsoft Docs"
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
  - "CA2122"
  - "DoNotIndirectlyExposeMethodsWithLinkDemands"
helpviewer_keywords: 
  - "CA2122"
  - "DoNotIndirectlyExposeMethodsWithLinkDemands"
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|  
|CheckId|CA2122|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 또는 protected 멤버에 [링크 요청](../Topic/Link%20Demands.md)이 있으며 보안 검사를 수행하지 않는 멤버에 의해 호출됩니다.  
  
## 규칙 설명  
 링크 요청은 직접 실행 호출자의 권한만 검사합니다.  멤버 `X`에서 호출자에 대해 보안 요청을 적용하지 않고 링크 요청으로 보호되는 코드를 호출하는 경우 필요한 권한이 없는 호출자가 `X`를 사용하여 보호되는 멤버에 액세스할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 보안 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md) 또는 링크 요청을 멤버에 추가하여 링크 요청으로 보호되는 멤버에 보안되지 않은 액세스가 제공되지 않도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에 따른 경고를 표시하지 않으려면 악용될 수 있는 작업이나 리소스에 대한 액세스 권한을 코드에서 호출자에게 부여하지 않는지 확인해야 합니다.  
  
## 예제  
 다음 예제에는 이 규칙을 위반하는 라이브러리와 해당 라이브러리의 취약성을 보여 주는 응용 프로그램이 나와 있습니다.  샘플 라이브러리에서는 함께 규칙을 위반하는 두 개의 메서드를 제공합니다.  여기서 링크 요청은 환경 변수에 대한 무제한 액세스로부터 `EnvironmentSetting` 메서드를 보호합니다.  `DomainInformation` 메서드는 `EnvironmentSetting`을 호출하기 전에는 호출자에 대해 보안 요청을 적용하지 않습니다.  
  
 [!code-cs[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]  
  
## 예제  
 다음 응용 프로그램은 보안되지 않은 라이브러리 멤버를 호출합니다.  
  
 [!code-cs[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **보안되지 않은 멤버의 값: seattle.corp.contoso.com**   
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [링크 요청](../Topic/Link%20Demands.md)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)