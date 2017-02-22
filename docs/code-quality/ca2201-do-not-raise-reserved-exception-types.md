---
title: "CA2201: 예약된 예외 형식을 발생시키지 마십시오. | Microsoft Docs"
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
  - "DoNotRaiseReservedExceptionTypes"
  - "CA2201"
helpviewer_keywords: 
  - "CA2201"
  - "DoNotRaiseReservedExceptionTypes"
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2201: 예약된 예외 형식을 발생시키지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotRaiseReservedExceptionTypes|  
|CheckId|CA2201|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드가 너무 일반적이거나 런타임에 예약된 예외 형식을 발생시킵니다.  
  
## 규칙 설명  
 다음 예외 형식은 너무 일반적이므로 사용자에게 그다지 충분한 정보를 제공하지 않습니다.  
  
-   <xref:System.Exception?displayProperty=fullName>  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.SystemException?displayProperty=fullName>  
  
 다음 예외 형식은 예약되어 있으므로 공용 언어 런타임을 통해서만 throw해야 합니다.  
  
-   <xref:System.ExecutionEngineException?displayProperty=fullName>  
  
-   <xref:System.IndexOutOfRangeException?displayProperty=fullName>  
  
-   <xref:System.NullReferenceException?displayProperty=fullName>  
  
-   <xref:System.OutOfMemoryException?displayProperty=fullName>  
  
 **일반 예외 throw하지 않음**  
  
 라이브러리나 프레임워크에서 <xref:System.Exception> 또는 <xref:System.SystemException>과 같은 일반 예외 형식을 throw할 경우 소비자는 처리 방법을 모르는 알 수 없는 예외를 포함하여 모든 예외를 catch해야 합니다.  
  
 대신 프레임워크에 이미 있는 더 많이 파생된 형식을 throw하거나 <xref:System.Exception>에서 파생되는 형식을 직접 만드십시오.  
  
 **특정 예외 throw**  
  
 다음 표에서는 매개 변수와 해당 매개 변수의 유효성을 검사할 때 throw할 예외를 보여 줍니다. 이러한 매개 변수에는 속성의 set 접근자에 있는 값 매개 변수가 포함됩니다.  
  
|매개 변수 설명|예외|  
|--------------|--------|  
|`null` 참조|<xref:System.ArgumentNullException?displayProperty=fullName>|  
|허용되는 값\(예: 컬렉션 또는 목록의 인덱스\) 범위를 벗어남|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|  
|잘못된 `enum` 값|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|  
|메서드의 매개 변수 사양\(예: `ToString(String)`의 형식 문자열\)에 맞지 않는 형식이 들어 있음|<xref:System.FormatException?displayProperty=fullName>|  
|그 밖의 잘못된 경우|<xref:System.ArgumentException?displayProperty=fullName>|  
  
 연산이 개체의 현재 상태에 대해 올바르지 않을 경우 \- <xref:System.InvalidOperationException?displayProperty=fullName>을 throw합니다.  
  
 삭제된 개체에서 연산이 수행될 경우 \- <xref:System.ObjectDisposedException?displayProperty=fullName>을 throw합니다.  
  
 연산이 지원되지 않는 경우\(예: 읽기 위해 연 스트림의 **Stream.Write**에서\) \- <xref:System.NotSupportedException?displayProperty=fullName>을 throw합니다.  
  
 변환으로 인해 오버플로가 발생할 경우\(예: 명시적 캐스트 연산자 오버로드에서\) \- <xref:System.OverflowException?displayProperty=fullName>을 throw합니다.  
  
 그 밖의 모든 경우에는 <xref:System.Exception>에서 파생되는 형식을 직접 만들고 해당 예외를 throw합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 throw된 예외의 형식을 예약된 형식이 아닌 다른 특정 형식으로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 관련 규칙  
 [CA1031: 일반적인 예외 형식을 catch하지 마십시오.](../Topic/CA1031:%20Do%20not%20catch%20general%20exception%20types.md)