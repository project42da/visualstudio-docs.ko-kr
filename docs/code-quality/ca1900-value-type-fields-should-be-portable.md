---
title: "CA1900: 값 형식 필드는 이식 가능해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1900"
  - "ValueTypeFieldsShouldBePortable"
helpviewer_keywords: 
  - "ValueTypeFieldsShouldBePortable"
  - "CA1900"
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1900: 값 형식 필드는 이식 가능해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ValueTypeFieldsShouldBePortable|  
|CheckId|CA1900|  
|범주|Microsoft.Portability|  
|변경 수준|주요 변경 \- 필드를 어셈블리 외부에서 볼 수 있는 경우<br /><br /> 주요 변경 아님 \- 필드가 어셈블리 외부에 표시되지 않는 경우|  
  
## 원인  
 이 규칙에서는 명시적 레이아웃으로 선언된 구조체가 64비트 운영 체제에서 비관리 코드로 마샬링될 때 올바르게 맞춰지는지 검사합니다.  IA\-64에서는 메모리 액세스 불일치를 허용하지 않으므로 이 위반 문제가 해결되지 않으면 프로세스가 충돌합니다.  
  
## 규칙 설명  
 불일치 필드를 포함하는 명시적 레이아웃이 있는 구조체는 64비트 운영 체제에서 충돌합니다.  
  
## 위반 문제를 해결하는 방법  
 8바이트보다 작은 모든 필드에는 해당 크기의 배수에 해당하는 오프셋이 있어야 하며 8바이트 이상인 필드에는 8의 배수에 해당하는 오프셋이 있어야 합니다.  다른 솔루션은 해당되는 경우 `LayoutKind.Explicit` 대신 `LayoutKind.Sequential`을 사용하는 것입니다.  
  
## 경고를 표시하지 않는 경우  
 이 경고는 오류에서 발생하는 경우에만 표시하지 않아야 합니다.