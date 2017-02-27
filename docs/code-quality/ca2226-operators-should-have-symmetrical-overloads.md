---
title: "CA2226: 연산자에는 대칭 오버로드가 있어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OperatorsShouldHaveSymmetricalOverloads"
  - "CA2226"
helpviewer_keywords: 
  - "CA2226"
  - "OperatorsShouldHaveSymmetricalOverloads"
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 14
---
# CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OperatorsShouldHaveSymmetricalOverloads|  
|CheckId|CA2226|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식이 같음 연산자 또는 같지 않음 연산자를 구현하면서 그 반대 연산자를 구현하지 않습니다.  
  
## 규칙 설명  
 같음 또는 같지 않음 연산을 형식 인스턴스에 적용할 수 있으면서 그 반대 연산자가 정의되어 있지 않은 경우는 없습니다.  형식은 대개 같음 연산자의 부정 값을 반환하여 같지 않음 연산자를 구현합니다.  
  
 C\# 컴파일러는 이 규칙을 위반할 경우 오류를 발생시킵니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 같음 연산자와 같지 않음 연산자를 모두 구현하거나 한 연산자만 있는 경우 이를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  해당 형식이 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서와 같은 방식으로 작동하지 않습니다.  
  
## 관련 규칙  
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)  
  
 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)