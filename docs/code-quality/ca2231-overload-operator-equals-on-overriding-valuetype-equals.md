---
title: "CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오. | Microsoft Docs"
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
  - "OverloadOperatorEqualsOnOverridingValueTypeEquals"
  - "CA2231"
  - "OverrideOperatorEqualsOnOverridingValueTypeEquals"
helpviewer_keywords: 
  - "CA2231"
  - "OverloadOperatorEqualsOnOverridingValueTypeEquals"
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|  
|CheckId|CA2231|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 값 형식이 <xref:System.Object.Equals%2A?displayProperty=fullName>를 재정의하지만 같음 연산자를 구현하지 않습니다.  
  
## 규칙 설명  
 대부분의 프로그래밍 언어에서는 값 형식에 대해 기본 구현된 같음 연산자\(\=\=\)가 없습니다.  사용 중인 프로그래밍 언어에서 연산자 오버로드를 지원하는 경우 같음 연산자를 구현할 것을 고려해 보아야 합니다.  그 동작은 <xref:System.Object.Equals%2A>의 동작과 같아야 합니다.  
  
 같음 연산자의 오버로드된 구현에서는 기본 같음 연산자를 사용할 수 없습니다.  기본 같음 연산자를 사용하면 스택 오버플로가 발생합니다.  같음 연산자를 구현하려면 구현에 Object.Equals 메서드를 사용합니다.  예를 들면 다음과 같습니다.  
  
```vb  
If (Object.ReferenceEquals(left, Nothing)) Then  
    Return Object.ReferenceEquals(right, Nothing)  
Else  
    Return left.Equals(right)  
End If  
```  
  
```c#  
if (Object.ReferenceEquals(left, null))   
    return Object.ReferenceEquals(right, null);  
return left.Equals(right);  
```  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 같음 연산자를 구현합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시하지 않아도 안전하지만 가능하면 같음 연산자를 제공하는 것이 좋습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 정의합니다.  
  
 [!code-cs[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]  
  
## 관련 규칙  
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)  
  
 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
## 참고 항목  
 <xref:System.Object.Equals%2A?displayProperty=fullName>