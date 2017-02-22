---
title: "CA2212: 서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오. | Microsoft Docs"
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
  - "CA2212"
  - "DoNotMarkServicedComponentsWithWebMethod"
helpviewer_keywords: 
  - "CA2212"
  - "DoNotMarkServicedComponentsWithWebMethod"
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2212: 서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotMarkServicedComponentsWithWebMethod|  
|CheckId|CA2212|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>에서 상속되는 형식의 메서드가 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>로 표시되었습니다.  
  
## 규칙 설명  
 <xref:System.Web.Services.WebMethodAttribute>는 ASP.NET을 사용하여 만든 XML Web services 내의 메서드에 적용됩니다. 이렇게 하면 원격 웹 클라이언트에서 메서드를 호출할 수 있습니다.  이 메서드 및 클래스는 public이어야 하며 ASP.NET 웹 응용 프로그램 내에서 실행되어야 합니다.  <xref:System.EnterpriseServices.ServicedComponent> 형식은 COM\+ 응용 프로그램에 의해 호스팅되며 COM\+ 서비스를 사용할 수 있습니다.  같은 시나리오에 사용하도록 설계된 것이 아니기 때문에 <xref:System.Web.Services.WebMethodAttribute>는 <xref:System.EnterpriseServices.ServicedComponent> 형식에 적용되지 않습니다.  다시 말해 이 특성을 <xref:System.EnterpriseServices.ServicedComponent> 메서드에 추가해도 원격 웹 클라이언트에서 메서드를 호출할 수 있는 것은 아닙니다.  <xref:System.Web.Services.WebMethodAttribute> 및 <xref:System.EnterpriseServices.ServicedComponent> 메서드에는 컨텍스트와 트랜잭션 흐름에 있어 충돌하는 동작 및 요구 사항이 있으므로 메서드의 동작이 일부 시나리오에서 잘못될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.EnterpriseServices.ServicedComponent> 메서드에서 해당 특성을 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  이러한 요소의 결합이 허용되는 시나리오는 없습니다.  
  
## 참고 항목  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>