---
title: "CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다. | Microsoft Docs"
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
  - "IdentifiersShouldDifferByMoreThanCase"
  - "CA1708"
helpviewer_keywords: 
  - "CA1708"
  - "IdentifiersShouldDifferByMoreThanCase"
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldDifferByMoreThanCase|  
|CheckId|CA1708|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 소문자로 변환했을 때 두 형식, 멤버, 매개 변수 또는 정규화된 네임스페이스의 이름이 서로 같습니다.  
  
## 규칙 설명  
 공용 언어 런타임을 대상으로 하는 언어는 대\/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대\/소문자만 달라서는 안 됩니다.  예를 들어 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 대\/소문자를 구분하지 않는 대표적인 언어입니다.  
  
 이 규칙은 공개된 멤버에 대해서만 실행됩니다.  
  
## 위반 문제를 해결하는 방법  
 대\/소문자를 구분하지 않고 다른 식별자와 비교했을 때 고유한 이름을 선택합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 사용 가능한 모든 언어에서 라이브러리를 사용하지 못할 수 있습니다.  
  
## 규칙 위반 예  
 다음 예제에서는 이 규칙에 대한 위반 내용을 보여 줍니다.  
  
 [!code-cs[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]  
  
## 관련 규칙  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)