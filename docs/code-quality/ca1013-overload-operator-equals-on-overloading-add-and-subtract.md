---
title: "CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오. | Microsoft Docs"
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
  - "OverrideOperatorEqualsOnOverridingAddAndSubtract"
  - "OverrideOperatorEqualsOnOverloadingAddAndSubtract"
  - "CA1013"
  - "OverloadOperatorEqualsOnOverloadingAddAndSubtract"
helpviewer_keywords: 
  - "OverrideOperatorEqualsOnOverloadingAddAndSubtract"
  - "OverrideOperatorEqualsOnOverridingAddAndSubtract"
  - "CA1013"
  - "OverloadOperatorEqualsOnOverloadingAddAndSubtract"
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|  
|CheckId|CA1013|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 또는 protected 형식이 같음 연산자를 구현하지 않고 더하기 또는 빼기 연산자를 구현합니다.  
  
## 규칙 설명  
 더하기 및 빼기 등과 같은 연산을 사용하여 형식의 인스턴스를 조합할 때는 구성 값이 같은 두 인스턴스에 대해 `true`가 반환되도록 거의 대부분의 경우 같음 연산을 정의해야 합니다.  
  
 같음 연산자의 오버로드된 구현에서는 기본 같음 연산자를 사용할 수 없습니다.  기본 같음 연산자를 사용하면 스택 오버플로가 발생합니다.  같음 연산자를 구현하려면 구현에 Object.Equals 메서드를 사용합니다.  다음 예제를 참조하십시오.  
  
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
 이 규칙 위반 문제를 해결하려면 더하기 및 빼기 연산자와 수학적으로 일관되도록 같음 연산자를 구현합니다.  
  
## 경고를 표시하지 않는 경우  
 같음 연산자의 기본 구현이 형식에 대해 올바른 동작을 제공하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식\(`BadAddableType`\)을 정의합니다.  이 형식은 필드 값이 같은 모든 두 인스턴스의 같음 테스트가 `true`가 되도록 같음 연산자를 구현해야 합니다.  `GoodAddableType` 형식은 수정된 구현을 보여 줍니다.  이 형식은 다른 규칙을 충족하기 위해 같지 않음 연산자도 구현하고 <xref:System.Object.Equals%2A>를 재정의합니다.  완전한 구현은 <xref:System.Object.GetHashCode%2A>도 구현합니다.  
  
 [!code-cs[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]  
  
## 예제  
 다음 예제에서는 이 항목의 앞에서 정의된 형식의 인스턴스로 같음을 테스트하여 같음 연산자에 대한 기본 동작과 올바른 동작을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **잘못된 형식: {2,2} {2,2}는 같습니까?  아니요**  
**올바른 형식: {3,3} {3,3}은 같습니까?  예**  
**올바른 형식: {3,3} {3,3}은 \=\= 입니까?   예**  
**잘못된 형식: {2,2} {9,9}는 같습니까?  아니요**  
**올바른 형식: {3,3} {9,9}는 \=\= 입니까?   아니요**    
## 참고 항목  
 [같음 연산자](../Topic/Equality%20Operators.md)