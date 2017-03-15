---
title: "CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오. | Microsoft Docs"
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
  - "DoNotOverloadOperatorEqualsOnReferenceTypes"
  - "CA1046"
helpviewer_keywords: 
  - "CA1046"
  - "DoNotOverloadOperatorEqualsOnReferenceTypes"
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|  
|CheckId|CA1046|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 중첩 public 참조 형식이 같음 연산자를 오버로드합니다.  
  
## 규칙 설명  
 참조 형식의 경우 같음 연산자의 기본 구현은 대부분 항상 올바릅니다.  기본적으로 두 참조는 같은 개체를 가리킬 경우에만 같습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 같음 연산자의 구현을 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 참조 형식이 기본 제공 값 형식과 비슷하게 동작할 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  형식 인스턴스에 대해 더하기 또는 빼기가 의미 있을 경우 같음 연산자를 구현하고 위반을 표시하지 않는 것이 올바를 수 있습니다.  
  
## 예제  
 다음 예제에서는 두 참조를 비교할 때의 기본 동작을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 몇 가지 참조를 비교합니다.  
  
 [!code-cs[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **a \= new \(2,2\) 및 b \= new \(2,2\)가 같습니까?  아니요**  
**c 및 a가 같습니까?  예**  
**b 및 a가 \=\=인 경우?  아니요**  
**c 및 a가 \=\=인 경우?  예**    
## 관련 규칙  
 [CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)  
  
## 참고 항목  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [같음 연산자](../Topic/Equality%20Operators.md)