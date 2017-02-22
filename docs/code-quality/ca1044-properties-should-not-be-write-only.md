---
title: "CA1044: 속성은 쓰기 전용이면 안 됩니다. | Microsoft Docs"
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
  - "PropertiesShouldNotBeWriteOnly"
  - "CA1044"
helpviewer_keywords: 
  - "CA1044"
  - "PropertiesShouldNotBeWriteOnly"
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1044: 속성은 쓰기 전용이면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PropertiesShouldNotBeWriteOnly|  
|CheckId|CA1044|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 속성에 set 접근자는 있지만 get 접근자가 없습니다.  
  
## 규칙 설명  
 get 접근자는 속성에 대한 읽기 권한을 제공하고 set 접근자는 쓰기 권한을 제공합니다.  읽기 전용 속성을 사용하는 것은 가능하고 종종 필요하기도 하지만 쓰기 전용 속성의 사용은 금지되어 있습니다.  이는 사용자가 값을 설정하도록 한 다음 값을 볼 수 있게 하면 값의 보안을 제공할 수 없기 때문입니다.  또한 읽기 권한이 없으면 공유 개체의 상태를 볼 수 없으므로 사용하는 데 제한을 받습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 속성에 get 접근자를 추가합니다.  또는, 쓰기 전용 속성의 동작이 필요한 경우 이 속성을 메서드로 변환할 것을 고려해 보십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하는 것이 좋습니다.  
  
## 예제  
 다음 예제에서는 `BadClassWithWriteOnlyProperty`이 쓰기 전용 속성을 가진 형식입니다.  `GoodClassWithReadWriteProperty`에는 올바른 코드가 들어 있습니다.  
  
 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
 [!code-cs[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]