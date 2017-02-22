---
title: "CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다. | Microsoft Docs"
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
  - "ResourceStringsShouldBeSpelledCorrectly"
  - "CA1703"
helpviewer_keywords: 
  - "CA1703"
  - "ResourceStringsShouldBeSpelledCorrectly"
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ResourceStringsShouldBeSpelledCorrectly|  
|CheckId|CA1703|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 리소스 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.  
  
## 규칙 설명  
 이 규칙은 리소스 문자열을 단어로 구문 분석\(복합 단어 토큰화\)하고 각 단어\/토큰의 맞춤법을 검사합니다.  구문 분석 알고리즘에 대한 자세한 내용은 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)를 참조하십시오.  
  
 기본적으로 영어 버전의 맞춤법 검사기가 사용됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 맞춤법이 올바른 완전한 단어를 사용하거나 단어를 사용자 지정 사전에 추가합니다.  사용자 지정 사전을 사용하는 방법에 대한 자세한 내용은 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  맞춤법이 올바른 단어를 사용하면 새 소프트웨어 라이브러리를 익히는 데 필요한 시간이 줄어듭니다.  
  
## 관련 규칙  
 [CA1701: 리소스 문자열 복합 단어는 정확한 대\/소문자를 사용해야 합니다.](../Topic/CA1701:%20Resource%20string%20compound%20words%20should%20be%20cased%20correctly.md)  
  
 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA2204: 리터럴의 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)