---
title: "CA1032: 표준 예외 생성자를 구현하십시오. | Microsoft Docs"
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
  - "CA1032"
  - "ImplementStandardExceptionConstructors"
helpviewer_keywords: 
  - "CA1032"
  - "ImplementStandardExceptionConstructors"
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1032: 표준 예외 생성자를 구현하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ImplementStandardExceptionConstructors|  
|CheckId|CA1032|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식이 <xref:System.Exception?displayProperty=fullName>을 확장고 필요한 모든 생성자를 선언하지 않습니다.  
  
## 규칙 설명  
 예외 형식은 다음과 같은 생성자를 구현해야 합니다.  
  
-   public NewException\(\)  
  
-   public NewException\(string\)  
  
-   public NewException\(string, Exception\)  
  
-   protected 또는 private NewException\(SerializationInfo, StreamingContext\)  
  
 이들 생성자 집합을 전부 제공하지 못하면 예외를 제대로 처리하기 어려울 수 있습니다.  예를 들어, `NewException(string, Exception)` 시그니처가 있는 생성자를 사용하여 다른 예외에 의해 발생하는 예외를 만들 수 있습니다.  이 생성자가 없으면 내부\(중첩\) 예외가 들어 있는 사용자 지정 예외의 인스턴스를 만들고 throw할 수 없습니다. 이러한 상황에서는 관리 코드에서 이 작업을 수행해야 합니다.  처음 세 개의 예외 생성자는 규칙에 따라 public입니다.  네 번째 생성자는 봉인되지 않은 클래스에서 protected이고 봉인 클래스에서 private입니다.  자세한 내용은 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)을 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 누락된 생성자를 예외에 추가하고 올바른 액세스 가능성을 갖는지 확인합니다.  
  
## 경고를 표시하지 않는 경우  
 public 생성자에 대해 서로 다른 액세스 수준을 사용함으로써 위반이 발생한 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에는 이 규칙을 위반하는 예외 형식과 올바로 구현된 예외 형식이 포함되어 있습니다.  
  
 [!code-cs[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]