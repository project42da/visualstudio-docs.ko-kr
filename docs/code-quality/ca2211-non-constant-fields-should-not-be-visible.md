---
title: "CA2211: 비상수 필드는 노출되면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2211"
  - "NonConstantFieldsShouldNotBeVisible"
helpviewer_keywords: 
  - "CA2211"
  - "NonConstantFieldsShouldNotBeVisible"
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2211: 비상수 필드는 노출되면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|NonConstantFieldsShouldNotBeVisible|  
|CheckId|CA2211|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected static 필드가 상수도 아니고 읽기 전용도 아닙니다.  
  
## 규칙 설명  
 상수도 아니고 읽기 전용도 아닌 static 필드는 스레드로부터 안전하지 않습니다.  이러한 필드에 대한 액세스는 신중하게 제어해야 하며 클래스 개체에 대한 액세스를 동기화하는 고급 프로그래밍 기술을 필요로 합니다.  이러한 기술은 배우기 어렵고 이러한 개체를 테스트하는 것은 그 자체로 위험하기 때문에 변경되지 않는 데이터를 저장하는 데에는 static 필드를 사용하는 것이 가장 좋습니다.  이 규칙은 라이브러리에 적용됩니다. 응용 프로그램에서는 모든 필드를 노출하면 안 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 static 필드를 상수 또는 읽기 전용으로 만듭니다.  이렇게 할 수 없으면 내부 필드에 대한 스레드 안전 액세스를 관리하는 스레드 안전 속성과 같은 대체 메커니즘을 사용하도록 형식을 다시 디자인합니다.  잠금 경합 및 교착 상태 같은 문제가 성능 및 라이브러리 동작에 영향을 줄 수 있다는 점을 알아 두어야 합니다.  
  
## 경고를 표시하지 않는 경우  
 현재 사용자가 응용 프로그램을 개발하고 있어서 static 필드를 포함하는 형식의 액세스에 대해 모든 권한을 가지면 이 규칙에서 경고를 표시하지 않아도 안전합니다.  라이브러리 디자이너는 이 규칙에서 경고를 표시해야 합니다. 비상수 static 필드를 사용하면 개발자가 라이브러리를 제대로 사용하기 어려워집니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-cs[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]