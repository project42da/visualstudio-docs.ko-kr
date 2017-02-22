---
title: "CA1809: 불필요한 로컬 항목을 사용하지 마십시오. | Microsoft Docs"
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
  - "CA1809"
  - "AvoidExcessiveLocals"
helpviewer_keywords: 
  - "AvoidExcessiveLocals"
  - "CA1809"
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1809: 불필요한 로컬 항목을 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidExcessiveLocals|  
|CheckId|CA1809|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 멤버에 64개가 넘는 지역 변수가 포함되어 있으며 일부는 컴파일러에 의해 생성되었을 수 있습니다.  
  
## 규칙 설명  
 값을 메모리가 아닌 프로세서 레지스터에 저장하는 방법은 성능 최적화에 많이 사용되는 방법이며 값의 *레지스터 등록*이라고도 합니다.  공용 언어 런타임에서는 최대 64개의 지역 변수를 레지스터에 저장할 수 있습니다.  레지스터에 등록되지 않은 변수는 스택에 놓이며 조작하기 전에 레지스터로 이동되어야 합니다.  모든 지역 변수가 레지스터에 등록될 수 있도록 하려면 지역 변수의 개수를 64개로 제한합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 64개 이하의 지역 변수만 사용하도록 구현을 리팩터링합니다.  
  
## 경고를 표시하지 않는 경우  
 성능이 중요하지 않은 경우에는 이 규칙에서 경고를 표시하지 않거나 이 규칙을 사용하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)