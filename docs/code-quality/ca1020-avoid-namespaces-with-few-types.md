---
title: "CA1020: 형식이 부족한 네임스페이스를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1020"
  - "AvoidNamespacesWithFewTypes"
helpviewer_keywords: 
  - "AvoidNamespacesWithFewTypes"
  - "CA1020"
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA1020: 형식이 부족한 네임스페이스를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidNamespacesWithFewTypes|  
|CheckId|CA1020|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 전역 네임스페이스 이외의 네임스페이스에 5개 미만의 형식이 포함되어 있습니다.  
  
## 규칙 설명  
 각 네임스페이스에 논리적 구성이 있는지, 낮은 밀도로 채워진 네임스페이스에 형식을 배치하는 타당한 근거가 있는지 확인합니다.  네임스페이스는 대부분의 시나리오에서 함께 사용되는 형식을 포함해야 합니다.  해당 응용 프로그램들이 서로 배타적인 경우 형식을 서로 구분된 네임스페이스에 배치해야 합니다.  예를 들어, <xref:System.Web.UI> 네임스페이스에는 웹 응용 프로그램에서 사용되는 형식이 포함되고 <xref:System.Windows.Forms> 네임스페이스에는 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] 기반 응용 프로그램에서 사용되는 형식이 포함됩니다.  두 네임 스페이스의 사용자 인터페이스 측면을 제어 하는 형식이 없더라도 이러한 형식은 같은 응용 프로그램에서 사용할 없도록 되어 있습니다.  따라서 별도 네임 스페이스에 있습니다.  또한 네임스페이스를 면밀하게 구성하면 기능을 쉽게 검색할 수 있으므로 유용합니다.  라이브러리 사용자는 네임스페이스 계층 구조를 검사하여 특정 기능을 구현하는 형식을 찾을 수 있어야 합니다.  
  
> [!NOTE]
>  이 지침을 따르기 위해 디자인 타임 형식 및 권한을 다른 네임스페이스에 병합해서는 안 됩니다.  이들 형식은 주 네임스페이스 아래의 해당 네임스페이스에 속하며 네임스페이스는 각각 `.Design` 및 `.Permissions`로 끝나야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 적은 수의 형식을 포함하는 네임스페이스를 하나의 네임스페이스로 결합합니다.  
  
## 경고를 표시하지 않는 경우  
 네임스페이스에 다른 네임스페이스의 형식과 함께 사용되는 형식이 포함되어 있지 않으면 이 규칙에서 경고를 표시하지 않아도 안전합니다.