---
title: "CA1065: 예기치 않은 위치에서 예외를 발생시키지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1065"
  - "DoNotRaiseExceptionsInUnexpectedLocations"
helpviewer_keywords: 
  - "DoNotRaiseExceptionsInUnexpectedLocations"
  - "CA1065"
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 16
---
# CA1065: 예기치 않은 위치에서 예외를 발생시키지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|  
|CheckId|CA1065|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 예외를 throw하지 않아야 하는 메서드가 예외를 throw했습니다.  
  
## 규칙 설명  
 예외를 throw하지 않아야 하는 메서드는 다음과 같은 범주로 나눌 수 있습니다.  
  
-   Property Get 메서드  
  
-   이벤트 접근자 메서드  
  
-   Equals 메서드  
  
-   GetHashCode 메서드  
  
-   ToString 메서드  
  
-   정적 생성자  
  
-   종료자  
  
-   Dispose 메서드  
  
-   같음 연산자  
  
-   암시적 캐스트 연산자  
  
 다음 단원에서는 이러한 메서드 형식에 대해 설명합니다.  
  
### Property Get 메서드  
 속성은 기본적으로 스마트 필드입니다.  따라서 속성은 가능한 한 필드처럼 작동합니다.  필드는 예외와 속성을 throw하지 않습니다.  예외를 throw하는 속성이 있는 경우 이 속성을 메서드로 사용하는 것이 좋습니다.  
  
 Property Get 메서드에서는 다음 예외를 throw할 수 있습니다.  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName> 및 모든 파생 항목\(<xref:System.ObjectDisposedException?displayProperty=fullName> 포함\)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName> 및 모든 파생 항목  
  
-   <xref:System.ArgumentException?displayProperty=fullName>\(인덱싱된 get에서만\)  
  
-   <xref:System.Collections.Generic.KeyNotFoundException>\(인덱싱된 get에서만\)  
  
### 이벤트 접근자 메서드  
 이벤트 접근자는 예외를 throw하지 않는 간단한 연산이어야 합니다.  이벤트 처리기를 추가하거나 제거할 때 이벤트에서 예외를 throw하지 않아야 합니다.  
  
 이벤트 접근자에서는 다음 예외를 throw할 수 있습니다.  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName> 및 모든 파생 항목\(<xref:System.ObjectDisposedException?displayProperty=fullName> 포함\)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName> 및 모든 파생 항목  
  
-   <xref:System.ArgumentException> 및 파생 항목  
  
### Equals 메서드  
 다음 **Equals** 메서드는 예외를 throw하지 않아야 합니다.  
  
-   <xref:System.Object.Equals%2A?displayProperty=fullName>  
  
-   [M:IEquatable.Equals](http://go.microsoft.com/fwlink/?LinkId=113472)  
  
 **Equals** 메서드는 예외를 throw하지 않고 `true` 또는 `false`를 반환해야 합니다.  예를 들어 일치하지 않는 두 형식이 Equals에 전달되면 <xref:System.ArgumentException>을 throw하지 않고 단순히 `false`를 반환해야 합니다.  
  
### GetHashCode 메서드  
 다음 **GetHashCode** 메서드는 일반적으로 예외를 throw하지 않아야 합니다.  
  
-   <xref:System.Object.GetHashCode%2A>  
  
-   [M:IEqualityComparer.GetHashCode\(T\)](http://go.microsoft.com/fwlink/?LinkId=113477)  
  
 **GetHashCode**는 항상 값을 반환해야 합니다.  이렇게 하지 않으면 해시 테이블의 항목이 손실될 수 있습니다.  
  
 인수를 사용하는 **GetHashCode**의 버전은 <xref:System.ArgumentException>을 throw할 수 있습니다.  그러나 **Object.GetHashCode**는 예외를 throw하지 않아야 합니다.  
  
### ToString 메서드  
 디버거는 <xref:System.Object.ToString%2A?displayProperty=fullName>을 사용하여 문자열 형식의 개체에 대한 정보를 표시합니다.  그러므로 **ToString**은 개체의 상태를 변경하지 않고 예외를 throw하지 않아야 합니다.  
  
### 정적 생성자  
 정적 생성자에서 예외를 throw하면 현재 응용 프로그램 도메인에서 해당 형식을 사용할 수 없습니다.  정적 생성자에서 예외를 throw하려면 보안 문제 같은 합당한 이유가 있어야 합니다.  
  
### 종료자  
 종료자에서 예외를 throw하면 CLR이 빨리 실패하고 이로 인해 프로세스가 종결됩니다.  따라서 종료자에서는 항상 예외를 throw하지 않아야 합니다.  
  
### Dispose 메서드  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드는 예외를 throw하지 않아야 합니다.  Dispose는 `finally` 절에서 정리 논리의 일부로 호출되는 경우가 많습니다.  그러므로 Dispose에서 예외를 명시적으로 throw하면 사용자가 `finally` 절 내에서 예외 처리를 추가해야 합니다.  
  
 **Dispose\(false\)** 코드 경로는 거의 항상 종료자에서 호출되므로 예외를 throw하지 않아야 합니다.  
  
### 같음 연산자\(\=\=, \!\=\)  
 같음 연산자는 Equals 메서드와 마찬가지로 `true` 또는 `false`를 반환하고 예외를 throw하지 않아야 합니다.  
  
### 암시적 캐스트 연산자  
 사용자는 암시적 캐스트 연산자가 호출되었음을 인식하지 못하는 경우가 많으므로 암시적 캐스트 연산자가 throw하는 예외는 전혀 예상할 수 없습니다.  그러므로 암시적 캐스트 연산자에서는 예외를 throw하지 않아야 합니다.  
  
## 위반 문제를 해결하는 방법  
 속성 getter의 경우 예외를 throw할 필요가 없도록 논리를 변경하거나 속성을 메서드로 변경합니다.  
  
 위에 나열된 다른 모든 메서드 형식의 경우 예외를 throw할 필요가 없도록 논리를 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 위반이 throw된 예외가 아닌 예외 선언으로 인한 것인 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA2219: exception 절에서 예외를 발생시키지 마십시오.](../Topic/CA2219:%20Do%20not%20raise%20exceptions%20in%20exception%20clauses.md)  
  
## 참고 항목  
 [디자인 경고](../code-quality/design-warnings.md)