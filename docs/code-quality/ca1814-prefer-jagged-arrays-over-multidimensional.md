---
title: "CA1814: 다차원 배열보다 가변 배열을 사용하십시오. | Microsoft Docs"
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
  - "PreferJaggedArraysOverMultidimensional"
  - "CA1814"
helpviewer_keywords: 
  - "CA1814"
  - "PreferJaggedArraysOverMultidimensional"
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1814: 다차원 배열보다 가변 배열을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PreferJaggedArraysOverMultidimensional|  
|CheckId|CA1814|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경|  
  
## 원인  
 멤버가 다차원 배열로 선언되었습니다.  
  
## 규칙 설명  
 가변 배열의 요소에는 배열이 사용됩니다.  요소를 구성하는 배열의 크기는 서로 다를 수 있습니다. 이 경우 일부 데이터 집합에 대한 공간을 절약할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 다차원 배열을 가변 배열로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 다차원 배열을 사용해도 공간이 낭비되지 않는 경우에는 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 가변 배열 및 다차원 배열의 선언을 보여 줍니다.  
  
 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-cs[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]