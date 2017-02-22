---
title: "CA1504: 잘못된 필드 이름을 검토하십시오. | Microsoft Docs"
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
  - "ReviewMisleadingFieldNames"
  - "CA1504"
helpviewer_keywords: 
  - "CA1504"
  - "ReviewMisleadingFieldNames"
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1504: 잘못된 필드 이름을 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewMisleadingFieldNames|  
|CheckId|CA1504|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 인스턴스 필드의 이름이 "s\_"로 시작하거나 `static` \([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Shared`\) 필드의 이름이 "m\_"로 시작합니다.  
  
## 규칙 설명  
 "s\_"로 시작하는 필드 이름은 여러 사용자에 의해 정적 데이터와 연결됩니다.  이와 마찬가지로 "m\_"로 시작하는 필드 이름은 인스턴스\(멤버\) 데이터와 연결됩니다.  쉬운 관리 코드의 경우 이름은 일반적으로 사용되는 규칙을 따라야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 적절한 접두사를 사용하여 필드의 이름을 바꿉니다  또는 `static` 한정자를 추가하거나 제거하여 필드를 현재 접미사에 맞게 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.