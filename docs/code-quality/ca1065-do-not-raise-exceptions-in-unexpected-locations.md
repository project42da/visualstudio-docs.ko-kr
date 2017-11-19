---
title: "CA1065: 예기치 않은 위치에서 예외를 발생 시 키 지 않는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3511778536bb9664726fc9a61b4773c209a0fd46
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065: 예기치 않은 위치에서 예외를 발생시키지 마십시오.
|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|  
|CheckId|CA1065|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 예외를 throw하지 않아야 하는 메서드가 예외를 throw했습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 예외를 throw 되지 않는 메서드를 다음과 같이 분류할 수 있습니다.  
  
-   속성 Get 메서드  
  
-   이벤트 접근자 메서드  
  
-   Equals 메서드  
  
-   GetHashCode 메서드  
  
-   ToString 메서드  
  
-   정적 생성자  
  
-   종료자  
  
-   Dispose 메서드  
  
-   같음 연산자  
  
-   암시적 캐스트 연산자  
  
 다음 섹션에서는 이러한 메서드 형식에 설명 합니다.  
  
### <a name="property-get-methods"></a>속성 Get 메서드  
 속성은 기본적으로 스마트 필드입니다. 따라서은 가능한 한 필드 처럼 동작 해야 합니다. 필드는 예외를 throw 하지 않습니다와 속성입니다. 예외를 throw 하는 속성이 있는 경우 메서드를 수행 하는 것이 좋습니다.  
  
 다음과 같은 예외 속성 get 메서드에서 throw 될 수 있습니다.  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>와 모든 파생 클래스 (포함 하 여 <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>와 모든 파생 클래스  
  
-   <xref:System.ArgumentException?displayProperty=fullName>(에서만 get 인덱싱된)  
  
-   <xref:System.Collections.Generic.KeyNotFoundException>(에서만 get 인덱싱된)  
  
### <a name="event-accessor-methods"></a>이벤트 접근자 메서드  
 이벤트 접근자에는 예외를 throw 하지 않는 간단한 작업 이어야 합니다. 이벤트 추가 또는 이벤트 처리기를 제거 하려고 할 때 예외를 throw 해서는 안 합니다.  
  
 다음 예외는 이벤트 접근자에서는에서 throw 될 수 있습니다.  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>와 모든 파생 클래스 (포함 하 여 <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>와 모든 파생 클래스  
  
-   <xref:System.ArgumentException>와 파생 클래스  
  
### <a name="equals-methods"></a>Equals 메서드  
 다음 **Equals** 메서드 예외를 throw 하지 않아야 합니다.  
  
-   <xref:System.Object.Equals%2A?displayProperty=fullName>  
  
-   [M:IEquatable.Equals](http://go.microsoft.com/fwlink/?LinkId=113472)  
  
 **Equals** 메서드를 반환 하도록 `true` 또는 `false` 예외를 throw 하는 대신 합니다. 예를 들어 Equals 일치 하지 않는 두 형식에 전달 되는 경우 방금 반환 해야 `false` throw 하는 대신는 <xref:System.ArgumentException>합니다.  
  
### <a name="gethashcode-methods"></a>GetHashCode 메서드  
 다음 **GetHashCode** 메서드 일반적으로 예외 throw 하지 않아야 합니다.  
  
-   <xref:System.Object.GetHashCode%2A>  
  
-   [M:IEqualityComparer.GetHashCode(T)](http://go.microsoft.com/fwlink/?LinkId=113477)  
  
 **GetHashCode** 항상 값을 반환 해야 합니다. 그렇지 않으면 해시 테이블에 있는 항목을 잃을 수 있습니다.  
  
 버전의 **GetHashCode** 인수 throw 할 수는 사용 하는 <xref:System.ArgumentException>합니다. 그러나 **Object.GetHashCode** 예외를 throw 하지 해야 합니다.  
  
### <a name="tostring-methods"></a>ToString 메서드  
 디버거를 사용 하 여 <xref:System.Object.ToString%2A?displayProperty=fullName> 문자열 형식의 개체에 대 한 정보를 표시할 수 있도록 합니다. 따라서 **ToString** 개체의 상태를 변경 하지 않아야 하 고 예외를 throw 하지 않아야 합니다.  
  
### <a name="static-constructors"></a>정적 생성자  
 정적 생성자에서 예외가 throw 발생은 현재 어플리케이션 도메인에 사용할 수 없는 것 형식이 있습니다. 정적 생성자에서 예외를 throw 하는 매우 좋은 이유 (예: 보안 문제) 있어야 합니다.  
  
### <a name="finalizers"></a>종료자  
 빨리 실패 하는 프로세스를 중지 하는 CLR 하면 종료자에서 예외를 throw 합니다. 따라서 종료자에서 예외를 throw 합니다. 항상 사용 하지 않아야 합니다.  
  
### <a name="dispose-methods"></a>Dispose 메서드  
 A <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드 예외를 throw 해서는 안 됩니다. 삭제가 정리에 논리의 일부로 자주 호출 되는 `finally` 절. 따라서 Dispose에서 예외를 throw 하는 명시적으로 설정 하면 사용자 내에서 예외 처리를 추가 하는 `finally` 절.  
  
 **와** 이 거의 항상 종료자에서 호출 되기 때문에 코드 경로 예외를 throw 하지 않아야 합니다.  
  
### <a name="equality-operators--"></a>같음 연산자 (= =,! =)  
 Equals 메서드와 마찬가지로 같음 연산자 반환 `true` 또는 `false` 하며 예외를 throw 하지 않아야 합니다.  
  
### <a name="implicit-cast-operators"></a>암시적 캐스트 연산자  
 사용자는 종종 암시적 캐스트 연산자가 호출 된 인식 하지 않으므로 암시적 캐스트 연산자에서 throw 된 예외가 완전히 예기치 않은 있습니다. 따라서 예외가 발생 하지 않을 암시적 캐스트 연산자에서 throw 되어야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 속성 getter에 대 한 논리를 변경 하거나 예외를 throw 하거나 메서드로 속성을 변경 하는 더 이상에 있도록 합니다.  
  
 다른 모든 메서드 종류 앞에 나열 된에 대 한는 논리를 변경 하 고 더 이상 예외를 throw 해야 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 예외를 발생 시키는 대신 예외 선언으로 위반이 발생 한 경우이 규칙에서는 경고를에서 표시 하지 않으려면 안전 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2219: exception 절에서 예외를 발생시키지 마십시오.](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)  
  
## <a name="see-also"></a>참고 항목  
 [디자인 경고](../code-quality/design-warnings.md)