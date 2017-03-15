---
title: "CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2218"
  - "OverrideGetHashCodeOnOverridingEquals"
helpviewer_keywords: 
  - "CA2218"
  - "OverrideGetHashCodeOnOverridingEquals"
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverrideGetHashCodeOnOverridingEquals|  
|CheckId|CA2218|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 형식이 <xref:System.Object.Equals%2A?displayProperty=fullName>를 재정의하지만 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>는 재정의하지 않습니다.  
  
## 규칙 설명  
 <xref:System.Object.GetHashCode%2A>는 현재 인스턴스를 기반으로 해싱 알고리즘 및 해시 테이블과 같은 데이터 구조체에 적합한 값을 반환합니다.  같은 형식의 동일한 두 개체가 같은 해시 코드를 반환해야 다음 형식의 인스턴스가 올바르게 작동한다고 할 수 있습니다.  
  
-   <xref:System.Collections.HashTable?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Dictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortList?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.HybredDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.IEqualityComparer?displayProperty=fullName>를 구현하는 형식  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Object.GetHashCode%2A>의 구현을 제공합니다.  형식이 같은 두 개체의 경우 이들 개체에 대한 <xref:System.Object.Equals%2A>의 구현이 `true`를 반환하는 경우 GetHashCode 구현이 같은 값을 반환하는지 확인해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 클래스 예제  
  
### 설명  
 다음 예제에서는 이 규칙을 위반하는 클래스\(참조 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]  
  
### 설명  
 다음 예제에서는 <xref:System.Object.GetHashCode>를 재정의하여 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]  
  
## 구조체 예제  
  
### 설명  
 다음 예제에서는 이 규칙을 위반하는 구조체\(값 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]  
  
### 설명  
 다음 예제에서는 <xref:System.Object.GetHashCode>를 재정의하여 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]  
  
## 관련 규칙  
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)  
  
 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)  
  
## 참고 항목  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Collections.HashTable?displayProperty=fullName>   
 [같음 연산자](../Topic/Equality%20Operators.md)