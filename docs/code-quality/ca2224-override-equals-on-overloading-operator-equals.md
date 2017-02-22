---
title: "CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오. | Microsoft Docs"
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
  - "CA2224"
  - "OverrideEqualsOnOverloadingOperatorEquals"
  - "OverrideEqualsOnOverridingOperatorEquals"
helpviewer_keywords: 
  - "CA2224"
  - "OverrideEqualsOnOverloadingOperatorEquals"
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|  
|CheckId|CA2224|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 형식이 같음 연산자를 구현하지만 <xref:System.Object.Equals%2A?displayProperty=fullName>를 재정의하지 않습니다.  
  
## 규칙 설명  
 같음 연산자는 간편한 구문을 통해 <xref:System.Object.Equals%2A> 메서드의 기능에 액세스할 수 있도록 제공됩니다.  같음 연산자를 구현할 경우 해당 논리는 <xref:System.Object.Equals%2A>의 논리와 같아야 합니다.  
  
 코드에서 이 규칙을 위반하면 C\# 컴파일러에서 경고를 발생시킵니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 같음 연산자의 구현을 제거하거나, <xref:System.Object.Equals%2A>를 재정의하고 두 메서드에서 같은 값을 반환하도록 해야 합니다.  같음 연산자가 일관된 동작을 나타내면 기본 클래스의 <xref:System.Object.Equals%2A> 메서드를 호출하는 <xref:System.Object.Equals%2A> 구현을 제공하여 이 위반 문제를 해결할 수 있습니다.  
  
## 경고를 표시하지 않는 경우  
 같음 연산자가 <xref:System.Object.Equals%2A>에서 상속된 구현과 같은 값을 반환하면 이 규칙에서 경고를 표시하지 않도록 설정해도 안전합니다.  예제 섹션에는 이 규칙에서 경고를 표시하지 않도록 안전하게 설정할 수 있는 형식이 들어 있습니다.  
  
## 일관되지 않은 같음 정의의 예제  
  
### 설명  
 다음 예제에서는 일관되지 않은 같음 정의 가진 형식을 보여 줍니다.  `BadPoint`는 같음 연산자의 사용자 지정 구현을 제공하여 같음의 의미를 변경하지만 <xref:System.Object.Equals%2A>를 재정의하지 않으므로 동일하게 동작합니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.OperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_1.cs)]  
  
## 예제  
 다음 코드에서는 `BadPoint`의 동작을 테스트합니다.  
  
 [!code-cs[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **a \=  \(\[0\] 1,1\) 및 b \= \(\[1\] 2,2\)가 같습니까?  아니요**  
**a \=\= b ?  아니요**  
**a1 및 a가 같습니까?  예**  
**a1 \=\= a ?  예**  
**b 및 bcopy가 같습니까?  아니요**  
**b \=\= bcopy ?  예**    
## 예제  
 다음 예제에서는 기술적으로 이 규칙을 위반하지만 일관된 방식으로 동작하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.ValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_3.cs)]  
  
## 예제  
 다음 코드에서는 `GoodPoint`의 동작을 테스트합니다.  
  
 [!code-cs[FxCop.Usage.TestValueTypeEquals#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_4.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **a \=  \(1,1\) 및 b \= \(2,2\)가 같습니까?  아니요**  
**a \=\= b ?  아니요**  
**a1 및 a가 같습니까?  예**  
**a1 \=\= a ?  예**  
**b 및 bcopy가 같습니까?  예**  
**b \=\= bcopy ?  예**    
## 클래스 예제  
  
### 설명  
 다음 예제에서는 이 규칙을 위반하는 클래스\(참조 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.OverrideEqualsClassViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_5.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.Object.Equals%2A?displayProperty=fullName>를 재정의하여 위반 문제를 해결합니다.  
  
 [!code-cs[FxCop.Usage.OverrideEqualsClassFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_6.cs)]  
  
## 구조체 예제  
  
### 설명  
 다음 예제에서는 이 규칙을 위반하는 구조체\(값 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.OverrideEqualsStructViolation#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_7.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.ValueType.Equals%2A?displayProperty=fullName>를 재정의하여 위반 문제를 해결합니다.  
  
 [!code-cs[FxCop.Usage.OverrideEqualsStructFixed#1](../code-quality/codesnippet/CSharp/ca2224-override-equals-on-overloading-operator-equals_8.cs)]  
  
## 관련 규칙  
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)  
  
 [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)