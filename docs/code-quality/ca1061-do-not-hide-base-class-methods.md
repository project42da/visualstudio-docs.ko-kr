---
title: "CA1061: 기본 클래스 메서드를 숨기지 마십시오. | Microsoft Docs"
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
  - "CA1061"
  - "DoNotHideBaseClassMethods"
helpviewer_keywords: 
  - "CA1061"
  - "DoNotHideBaseClassMethods"
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1061: 기본 클래스 메서드를 숨기지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotHideBaseClassMethods|  
|CheckId|CA1061|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 파생된 형식에서 이름과 매개 변수 수가 기본 메서드와 같은 메서드를 선언합니다. 매개 변수 중 하나 이상이 기본 메서드에 있는 해당 매개 변수의 기본 형식입니다. 또한 나머지 매개 변수의 형식은 기본 메서드의 해당 매개 변수와 동일합니다.  
  
## 규칙 설명  
 파생된 메서드의 매개 변수 시그니처가 기본 메서드의 매개 변수 시그니처에 있는 해당 형식보다 더 약하게 파생된 형식이라는 점만 다른 경우 기본 형식의 메서드는 파생된 형식에 있는 동일한 이름의 메서드에 의해 숨겨집니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 제거하거나 메서드 이름을 바꿉니다. 또는 메서드가 기본 메서드를 숨기지 않도록 매개 변수 시그니처를 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]