---
title: "CA1804: 사용되지 않는 로컬 항목을 제거하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1804"
  - "RemoveUnusedLocals"
helpviewer_keywords: 
  - "RemoveUnusedLocals"
  - "CA1804"
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1804: 사용되지 않는 로컬 항목을 제거하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|RemoveUnusedLocals|  
|CheckId|CA1804|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 지역 변수를 선언하지만 할당문에서 값을 받는 용도 이외로는 해당 변수를 사용하지 않습니다.  이 규칙에 따라 분석하려면 테스트한 어셈블리가 디버깅 정보와 함께 빌드되고 관련 프로그램 데이터베이스 파일\(.pdb\)을 사용할 수 있어야 합니다.  
  
## 규칙 설명  
 사용되지 않는 지역 변수와 불필요한 할당으로 어셈블리의 크기가 증가하고 성능이 저하될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 지역 변수를 제거하거나 사용합니다.  [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]에 포함된 C\# 컴파일러는 `optimize` 옵션이 사용될 경우 사용되지 않는 지역 변수를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 컴파일러에서 변수를 내보낸 경우에는 이 규칙에서 경고를 표시하지 마십시오.  또한 성능 및 코드 유지 관리가 그다지 중요하지 않을 경우 이 규칙에서 경고를 표시하지 않거나 규칙을 사용하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 사용되지 않는 지역 변수 몇 가지를 보여 줍니다.  
  
 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-cs[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]  
  
## 관련 규칙  
 [CA1809: 불필요한 로컬 항목을 사용하지 마십시오.](../code-quality/ca1809-avoid-excessive-locals.md)  
  
 [CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../Topic/CA1812:%20Avoid%20uninstantiated%20internal%20classes.md)  
  
 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../Topic/CA1801:%20Review%20unused%20parameters.md)