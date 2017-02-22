---
title: "CA1713: 이벤트에 Before 또는 After 접두사를 사용하지 마십시오. | Microsoft Docs"
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
  - "EventsShouldNotHaveBeforeOrAfterPrefix"
  - "CA1713"
helpviewer_keywords: 
  - "CA1713"
  - "EventsShouldNotHaveBeforeOrAfterPrefix"
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1713: 이벤트에 Before 또는 After 접두사를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|  
|CheckId|CA1713|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 이벤트 이름이 'Before' 또는 'After'로 시작합니다.  
  
## 규칙 설명  
 이벤트 이름은 해당 이벤트를 발생시키는 동작을 나타내야 합니다.  특정 시퀀스에서 발생하는 관련 이벤트의 이름을 지정하려면 현재 또는 과거 시제를 사용하여 동작 시퀀스 내의 상대적인 위치를 나타냅니다.  예를 들어, 리소스를 닫을 때 발생하는 한 쌍의 이벤트 이름을 지정할 경우 'BeforeClose' 및 'AfterClose' 대신 'Closing' 및 'Closed'로 지정할 수 있습니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 이벤트 이름에서 접두사를 제거하고 동사의 현재 또는 과거 시제를 사용하여 이름을 변경하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.