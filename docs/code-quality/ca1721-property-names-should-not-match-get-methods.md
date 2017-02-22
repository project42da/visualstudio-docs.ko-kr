---
title: "CA1721: 속성 이름은 Get 메서드와 달라야 합니다. | Microsoft Docs"
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
  - "CA1721"
  - "PropertyNamesShouldNotMatchGetMethods"
helpviewer_keywords: 
  - "CA1721"
  - "PropertyNamesShouldNotMatchGetMethods"
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1721: 속성 이름은 Get 메서드와 달라야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PropertyNamesShouldNotMatchGetMethods|  
|CheckId|CA1721|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 멤버의 이름이 'Get'으로 시작하며 이름의 나머지 부분이 public 또는 protected 속성의 이름과 같습니다.  예를 들어, 'GetColor'라는 이름의 메서드와 'Color'라는 이름의 속성이 포함된 형식은 이 규칙을 위반합니다.  
  
## 규칙 설명  
 Get 메서드와 속성은 서로가 분명히 구분되는 이름을 사용해야 합니다.  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이를 통해 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간이 단축되고, 관리 코드 개발에 대한 전문 지식을 갖춘 작업자가 라이브러리를 개발했다는 신뢰성이 향상됩니다.  
  
## 위반 문제를 해결하는 방법  
 접두사가 'Get'인 메서드의 이름과 같지 않은 이름으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
> [!NOTE]
>  IExtenderProvider 인터페이스를 구현하여 Get 메서드가 호출되는 경우 이 경고가 제외될 수 있습니다.  
  
## 예제  
 다음 예제에는 이 규칙을 위반하는 메서드와 속성이 포함되어 있습니다.  
  
 [!code-cs[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]  
  
## 관련 규칙  
 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)