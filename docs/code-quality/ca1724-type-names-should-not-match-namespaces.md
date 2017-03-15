---
title: "CA1724: 형식 이름은 네임스페이스와 달라야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TypeNamesShouldNotMatchNamespaces"
  - "CA1724"
helpviewer_keywords: 
  - "TypeNamesShouldNotMatchNamespaces"
  - "CA1724"
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA1724: 형식 이름은 네임스페이스와 달라야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TypeNamesShouldNotMatchNamespaces|  
|CheckId|CA1724|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 대\/소문자를 구분하지 않고 비교할 경우 형식 이름이 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 네임스페이스 이름과 일치합니다.  
  
## 규칙 설명  
 형식 이름은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리에 정의된 네임스페이스의 이름과 같아서는 안 됩니다.  이 규칙을 위반하면 라이브러리의 유용성이 저하될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리 네임스페이스의 이름과 같지 않은 형식 이름을 선택합니다.  
  
## 경고를 표시하지 않는 경우  
 새로 개발하는 경우 이 규칙에서 경고를 표시하지 않아야 하는 시나리오는 알려져 있지 않습니다.  경고가 표시되지 않도록 하려면 라이브러리의 사용자가 일치하는 이름으로 혼동할 수 있을지 신중하게 고려하십시오.  제공되는 라이브러리의 경우에는 이 규칙에서 경고를 표시하지 않아야 할 수 있습니다.