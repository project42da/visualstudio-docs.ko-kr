---
title: "CA1716: 식별자는 키워드와 달라야 합니다. | Microsoft Docs"
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
  - "IdentifiersShouldNotMatchKeywords"
  - "CA1716"
helpviewer_keywords: 
  - "IdentifiersShouldNotMatchKeywords"
  - "CA1716"
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1716: 식별자는 키워드와 달라야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldNotMatchKeywords|  
|CheckId|CA1716|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 네임스페이스, 형식 또는 가상 또는 인터페이스 멤버의 이름이 프로그래밍 언어의 예약된 키워드와 일치합니다.  
  
## 규칙 설명  
 네임스페이스, 형식 및 가상 및 인터페이스 멤버에 대한 식별자는 공용 언어 런타임을 대상으로 하는 언어에서 정의된 키워드와 일치하면 안 됩니다.  사용 중인 언어와 키워드에 따라 컴파일러 오류 및 모호성으로 인해 라이브러리를 사용하기 어려울 수 있습니다.  
  
 이 규칙은 다음 언어의 키워드를 확인합니다.  
  
-   Visual Basic  
  
-   C\#  
  
-   C\+\+\/CLI  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 키워드의 경우 대\/소문자를 구분하지 않는 비교가 사용되고 다른 언어의 경우 대\/소문자를 구분하는 비교가 사용됩니다.  
  
## 위반 문제를 해결하는 방법  
 키워드 목록에 표시되지 않는 이름을 선택합니다.  
  
## 경고를 표시하지 않는 경우  
 식별자가 API의 사용자를 혼동하지 않고 라이브러리를 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서 사용 가능한 모든 언어에서 사용할 수 있다고 확신하는 경우 이 규칙에서 경고를 표시하지 않을 수 있습니다.