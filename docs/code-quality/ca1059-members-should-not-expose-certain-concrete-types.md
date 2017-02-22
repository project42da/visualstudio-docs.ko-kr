---
title: "CA1059: 멤버는 구체적인 특정 형식을 노출하면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1059"
  - "MembersShouldNotExposeCertainConcreteTypes"
helpviewer_keywords: 
  - "CA1059"
  - "MembersShouldNotExposeCertainConcreteTypes"
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1059: 멤버는 구체적인 특정 형식을 노출하면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MembersShouldNotExposeCertainConcreteTypes|  
|CheckId|CA1059|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 멤버가 구체적인 특정 형식이거나 매개 변수 중 하나 또는 반환 값을 통해 구체적인 특정 형식을 노출합니다.  현재 이 규칙은 다음과 같은 구체적인 형식의 노출을 보고합니다.  
  
-   <xref:System.Xml.XmlNode?displayProperty=fullName>에서 파생된 형식입니다.  
  
## 규칙 설명  
 구체적인 형식은 완전히 구현되었기 때문에 인스턴스화할 수 있는 형식을 말합니다.  멤버를 광범위하게 사용할 수 있도록 하려면 구체적인 형식을 제안된 인터페이스로 바꾸십시오.  이렇게 하면 멤버가 해당 인터페이스를 구현하는 모든 형식을 받아들이거나, 해당 인터페이스를 구현하는 형식이 필요한 곳에 멤버를 사용할 수 있게 됩니다.  
  
 다음 표에서는 대상으로 지정된 구체적인 형식과 해당 형식에 대해 제안된 대체 인터페이스를 나열합니다.  
  
|구체적인 형식|바꾸기|  
|-------------|---------|  
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> 이 인터페이스를 사용하면 XML 데이터 소스의 특정 구현에서 멤버가 분리됩니다.|  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 구체적인 형식을 제안된 인터페이스로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 구체적인 형식에서 제공하는 특정 기능이 필요한 경우에는 이 규칙에서 메시지를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1011: 기본 형식을 매개 변수로 전달해 보십시오.](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)