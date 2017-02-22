---
title: "CA1506: 클래스 결합을 지나치게 많이 사용하지 마십시오. | Microsoft Docs"
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
  - "AvoidExcessiveClassCoupling"
  - "CA1506"
helpviewer_keywords: 
  - "AvoidExcessiveClassCoupling"
  - "CA1506"
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1506: 클래스 결합을 지나치게 많이 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경|  
  
## 원인  
 형식 또는 메서드가 다른 여러 형식과 결합되었습니다.  
  
## 규칙 설명  
 이 규칙은 형식 또는 메서드에 들어 있는 고유한 형식 참조의 개수를 계산하여 클래스 결합을 측정합니다.  
  
 클래스 결합이 많은 형식 및 메서드는 유지 관리하기가 어려울 수 있습니다.  결합력은 낮고 응집력은 높은 형식 및 메서드를 사용하는 것이 좋습니다.  
  
## 위반 문제를 해결하는 방법  
 이 위반 문제를 해결하려면 형식 또는 메서드를 다시 디자인하여 결합되는 형식의 수를 줄여 봅니다.  
  
## 경고를 표시하지 않는 경우  
 형식 또는 메서드의 다른 형식에 대한 의존도가 높더라도 유지 관리가 가능한 것으로 간주되면 이 경고를 제외합니다.  
  
## 참고 항목  
 [유지 관리 경고](../code-quality/maintainability-warnings.md)   
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)