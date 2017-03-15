---
title: "CA1036: 비교 가능한 형식에 메서드를 재정의하십시오. | Microsoft Docs"
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
  - "CA1036"
  - "OverrideMethodsOnComparableTypes"
helpviewer_keywords: 
  - "OverrideMethodsOnComparableTypes"
  - "CA1036"
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1036: 비교 가능한 형식에 메서드를 재정의하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OverrideMethodsOnComparableTypes|  
|CheckId|CA1036|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 또는 protected 형식에서 <xref:System.IComparable?displayProperty=fullName> 인터페이스를 구현하고, <xref:System.Object.Equals%2A?displayProperty=fullName>를 재정의하지 않거나 같음, 같지 않음, 보다 작음 또는 보다 큼에 대한 언어별 연산자를 오버로드하지 않습니다.  이 규칙에서는 형식이 인터페이스의 구현만 상속하는 경우 위반을 보고하지 않습니다.  
  
## 규칙 설명  
 사용자 지정 정렬 순서를 정의하는 형식은 <xref:System.IComparable> 인터페이스를 구현합니다.  <xref:System.IComparable.CompareTo%2A> 메서드는 해당 형식의 두 인스턴스에 대한 적절한 정렬 순서를 나타내는 정수 값을 반환합니다.  이 규칙에서는 정렬 순서를 설정하는 형식을 식별하며 이것은 같음, 같지 않음, 보다 작음 및 보다 큼의 일반적인 의미가 적용되지 않는다는 것을 나타냅니다.  <xref:System.IComparable>의 구현을 제공하는 경우 <xref:System.Object.Equals%2A>도 재정의하여 <xref:System.IComparable.CompareTo%2A>와 일관된 값을 반환하도록 해야 합니다.  <xref:System.Object.Equals%2A>를 재정의하고 연산자 오버로드를 지원하는 언어로 코딩하는 경우 <xref:System.Object.Equals%2A>와 일관성 있는 연산자도 제공해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Object.Equals%2A>를 재정의합니다.  사용하는 프로그래밍 언어에서 연산자 오버로드를 지원하는 경우 다음 연산자를 제공합니다.  
  
-   op\_Equality  
  
-   op\_Inequality  
  
-   op\_LessThan  
  
-   op\_GreaterThan  
  
 C\#에서 이들 연산자를 나타내는 데 사용되는 토큰은 \=\=, \!\=, \<, and \>입니다.  
  
## 경고를 표시하지 않는 경우  
 Visual Basic .NET에서와 마찬가지로 연산자가 없어서 위반이 발생하였고 프로그래밍 언어에서 연산자 오버로드를 지원하지 않는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  연산자 구현이 응용 프로그램 컨텍스트에서 의미가 없다고 판단되는 경우 op\_Equality 이외의 같음 연산자에서 발생할 때 이 규칙에서 경고를 표시하지 않는 것도 안전합니다.  그러나 Object.Equals를 재정의하는 경우 항상 op\_Equality 및 \=\= 연산자 위에 있어야 합니다.  
  
## 예제  
 다음 예제에는 <xref:System.IComparable>을 올바르게 구현하는 형식이 포함되어 있습니다.  코드 주석을 통해 <xref:System.Object.Equals%2A> 및 <xref:System.IComparable> 인터페이스에 관련된 다양한 규칙을 충족하는 메서드를 식별할 수 있습니다.  
  
 [!code-cs[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 앞에 나온 <xref:System.IComparable> 구현의 동작을 테스트합니다.  
  
 [!code-cs[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]  
  
## 참고 항목  
 <xref:System.IComparable?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [같음 연산자](../Topic/Equality%20Operators.md)