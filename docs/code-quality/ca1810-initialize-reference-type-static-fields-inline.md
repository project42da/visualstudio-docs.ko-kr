---
title: "CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitializeReferenceTypeStaticFieldsInline"
  - "CA1810"
helpviewer_keywords: 
  - "InitializeReferenceTypeStaticFieldsInline"
  - "CA1810"
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 21
---
# CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|InitializeReferenceTypeStaticFieldsInline|  
|CheckId|CA1810|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 참조 형식에서 명시적인 정적 생성자를 선언합니다.  
  
## 규칙 설명  
 형식이 명시적인 정적 생성자를 선언하면 JIT\(Just\-in\-Time\) 컴파일러는 형식의 각 정적 메서드와 인스턴스 생성자에 검사를 추가하여 정적 생성자를 이전에 호출했는지 확인합니다.  정적 멤버에 액세스하거나 형식의 인스턴스를 만들면 정적 초기화가 트리거됩니다.  그러나 형식 변수를 선언만 하고 사용하지 않으면 정적 초기화가 트리거되지 않습니다. 이 점은 초기화를 통해 전역 상태가 변경될 경우 중요할 수 있습니다.  
  
 모든 정적 데이터가 인라인으로 초기화되고 명시적인 정적 생성자가 선언되지 않은 경우에는 MSIL\(Microsoft Intermediate Language\) 컴파일러가 정적 데이터를 초기화하는 암시적인 정적 생성자와 `beforefieldinit` 플래그를 MSIL 형식 정의에 추가합니다.  JIT 컴파일러가 `beforefieldinit` 플래그를 발견하면 대부분의 경우 정적 생성자 검사가 추가되지 않은 것입니다.  정적 필드에 액세스하기 전에는 정적 초기화가 반드시 발생하지만 정적 메서드 또는 인스턴스 생성자를 호출하기 전에는 정적 초기화가 반드시 발생한다는 보장이 없습니다.  정적 초기화는 형식 변수가 선언된 후 언제든지 발생할 수 있습니다.  
  
 정적 생성자 검사로 인해 성능이 저하될 수 있습니다.  정적 생성자는 종종 정적 필드를 초기화하는 데만 사용됩니다. 이 경우 정적 필드의 첫 번째 액세스 전에 정적 초기화가 발생하도록 만들기만 하면 됩니다.  이들 형식과 대부분의 다른 형식에는 `beforefieldinit` 동작이 적합합니다.  적합하지 않은 경우는 정적 초기화가 전역 상태에 영향을 주고 다음 중 하나에 해당될 때입니다.  
  
-   전역 상태에 미치는 영향이 너무 크고 해당 형식이 사용되지 않을 경우 전역 상태 정보가 필요 없습니다.  
  
-   해당 형식의 정적 필드에 액세스하지 않고도 전역 상태 정보에 액세스할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 성능 문제가 그다지 중요하지 않을 경우, 정적 초기화로 인해 전역 상태가 너무 많이 변경되는 경우, 형식의 정적 메서드가 호출되거나 형식 인스턴스가 만들어지기 전에 정적 초기화가 이루어져야 하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 `StaticConstructor` 형식과 정적 생성자를 인라인 초기화로 바꿔 규칙을 만족하는 `NoStaticConstructor` 형식을 보여 줍니다.  
  
 [!CODE [FxCop.Performance.RefTypeStaticCtor#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Performance.RefTypeStaticCtor#1)]  
  
 `NoStaticConstructor` 클래스의 MSIL 정의에 `beforefieldinit` 플래그가 추가된 것을 볼 수 있습니다.  
  
  **.class public auto ansi StaticConstructor**  
 **extends \[mscorlib\]System.Object**  
**{**  
**} \/\/ 클래스 StaticConstructor의 끝**  
**.class public auto ansi beforefieldinit NoStaticConstructor**  
 **extends \[mscorlib\]System.Object**  
**{**  
**} \/\/ 클래스 NoStaticConstructor의 끝**   
## 관련 규칙  
 [CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오.](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)