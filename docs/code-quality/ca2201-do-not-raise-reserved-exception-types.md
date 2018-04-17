---
title: 'CA2201: 예약 된 예외 형식을 발생 시 키 지 않는 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd95bedc273a14d9b3d455db5fd25eac1cf74aa4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: 예약된 예외 형식을 발생시키지 마십시오.
|||  
|-|-|  
|TypeName|DoNotRaiseReservedExceptionTypes|  
|CheckId|CA2201|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 메서드를 너무 일반적 또는 런타임에서 예약 된 예외 형식을 발생 시킵니다.  
  
## <a name="rule-description"></a>규칙 설명  
 사용자에 게 충분 한 정보를 제공 하기는 너무 일반적 다음 예외 유형은 다음과 같습니다.  
  
-   <xref:System.Exception?displayProperty=fullName>  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.SystemException?displayProperty=fullName>  
  
 다음 예외 형식 예약 되어 있으므로 공용 언어 런타임에서 throw 됩니다.  
  
-   <xref:System.ExecutionEngineException?displayProperty=fullName>  
  
-   <xref:System.IndexOutOfRangeException?displayProperty=fullName>  
  
-   <xref:System.NullReferenceException?displayProperty=fullName>  
  
-   <xref:System.OutOfMemoryException?displayProperty=fullName>  
  
 **일반 예외를 Throw 하지 않습니다**  
  
 일반 예외 유형을 같은 throw 하는 경우 <xref:System.Exception> 또는 <xref:System.SystemException> 라이브러리 또는 프레임 워크에서는 사용자가를 모두 catch 강제로 예외를 처리 하는 방법을 알지 못할 알 수 없는 예외를 포함 합니다.  
  
 대신, 프레임 워크에 이미 있는 더 많이 파생 된 형식을 throw 또는에서 파생 된 사용자 정의 형식을 만들 <xref:System.Exception>합니다.  
  
 **특정 예외를 throw 합니다.**  
  
 다음 표에서 매개 변수를 표시 하 고 예외를 throw 하는 속성의 set 접근자에 값 매개 변수를 포함 하는 매개 변수 유효성을 검사할 때:  
  
|매개 변수 설명|예외|  
|---------------------------|---------------|  
|`null` 참조|<xref:System.ArgumentNullException?displayProperty=fullName>|  
|값 (예: 컬렉션 또는 목록의 대 한 인덱스)의 허용된 범위를 벗어납니다.|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|  
|잘못 된 `enum` 값|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|  
|메서드의 매개 변수 사양에 맞지 않는 형식이 포함 되어 있는 (형식 문자열과 같은 `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|  
|유효 하지 않음|<xref:System.ArgumentException?displayProperty=fullName>|  
  
 작업 개체 throw의 현재 상태에 대해 유효 하지 않은 경우 <xref:System.InvalidOperationException?displayProperty=fullName>  
  
 삭제 된 개체에서 연산이 수행 될 때 throw <xref:System.ObjectDisposedException?displayProperty=fullName>  
  
 작업이 지원 되지 않는 경우 (예: 재정의 된 **Stream.Write** 읽기용으로 열 스트림의) throw <xref:System.NotSupportedException?displayProperty=fullName>  
  
 (예: 명시적 캐스트 연산자 오버 로드) 오버플로가 변환으로 인해 throw <xref:System.OverflowException?displayProperty=fullName>  
  
 다른 모든 상황에서 파생 되는 형식을 직접 만드는 것이 좋습니다 <xref:System.Exception> 해당 예외를 throw 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 예약 된 형식 중 하나가 아닙니다 특정 형식에 throw 된 예외의 종류를 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1031: 일반적인 예외 형식을 catch하지 마십시오.](../code-quality/ca1031-do-not-catch-general-exception-types.md)