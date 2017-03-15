---
title: "CA2204: 리터럴의 철자가 맞아야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Literals should be spelled correctly"
  - "CA2204"
  - "LiteralsShouldBeSpelledCorrectly"
helpviewer_keywords: 
  - "CA2204"
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA2204: 리터럴의 철자가 맞아야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|LiteralsShouldBeSpelledCorrectly|  
|CheckId|CA2204|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드는 지역화된 문자열을 필요로 하는 매개 변수 또는 속성에 사용되는 리터럴 문자열을 전달하고 리터럴 문자열에는 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.  
  
## 규칙 설명  
 이 규칙에서는 다음 사례 중 하나 이상이 참일 때 매개 변수 또는 속성에 대한 값으로 전달되는 리터럴 문자열을 검사합니다.  
  
-   매개 변수 또는 속성의 <xref:System.ComponentModel.LocalizableAttribute> 특성은 true로 설정됩니다.  
  
-   매개 변수 또는 속성 이름에 "Text", "Message" 또는 "Caption"이 포함되어 있습니다.  
  
-   Console.Write or Console.WriteLine 메서드에 전달되는 문자열 매개 변수의 이름은 "값" 또는 "형식"입니다.  
  
 이 규칙은 복합 단어를 토큰화하여 리터럴 문자열을 단어로 구문 분석하고 각 단어\/토큰의 맞춤법을 검사합니다.  구문 분석 알고리즘에 대한 자세한 내용은 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)를 참조하십시오.  
  
 기본적으로 영어 버전의 맞춤법 검사기가 사용됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 단어의 맞춤법을 수정하거나 단어를 사용자 지정 사전에 추가합니다.  사용자 지정 사전을 사용하는 방법에 대한 자세한 내용은 [방법: 코드 분석 사전 사용자 지정](../Topic/How%20to:%20Customize%20the%20Code%20Analysis%20Dictionary.md)를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  맞춤법이 올바른 단어를 사용하면 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간이 줄어듭니다.  
  
## 관련 규칙  
 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)