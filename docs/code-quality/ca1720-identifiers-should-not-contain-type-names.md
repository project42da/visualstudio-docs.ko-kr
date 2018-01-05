---
title: "CA1720: 식별자 이름을 포함 하면 안 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ac50c390ca7a45cf5ef28f2d82d1f75fc5e2c1a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: 식별자에 형식 이름을 포함하면 안 됩니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainTypeNames|  
|CheckId|CA1720|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 멤버의 매개 변수 이름에는 데이터 형식 이름이 들어 있습니다.  
  
 또는  
  
 외부에서 볼 수 있는 멤버의 이름에 언어 특정 데이터 형식 이름을 포함합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 매개 변수 및 멤버 이름 보다 잘 개발 도구에서 제공 하는 형식을 설명 하는 용도 보다는 의미를 통신에 사용 합니다. 멤버 이름에 대 한 데이터 형식 이름을 사용 해야 하는 경우 언어별로 대신 언어 독립적인 이름을 사용 합니다. 예를 들어 C# 형식 이름 'int', 대신 언어 독립적인 데이터 형식 이름, i n t 32를 사용 합니다.  
  
 매개 변수 또는 멤버 이름의 개별 토큰은 대/소문자 다음 언어 특정 데이터 형식 이름에 대해 확인 됩니다.  
  
-   Bool  
  
-   WChar  
  
-   Int8  
  
-   UInt8  
  
-   Short  
  
-   UShort  
  
-   Int  
  
-   UInt  
  
-   정수  
  
-   UInteger  
  
-   Long  
  
-   ULong  
  
-   부호 없음  
  
-   서명  
  
-   Float  
  
-   Float32  
  
-   Float64  
  
 또한 매개 변수 이름은 비교 하 여 확인은 다음 언어에 관계 없이 데이터 형식 이름과 대/소문자:  
  
-   개체  
  
-   obj  
  
-   부울  
  
-   Char  
  
-   문자열  
  
-   SByte  
  
-   Byte  
  
-   UByte  
  
-   Int16  
  
-   UInt16  
  
-   Int32  
  
-   UInt32  
  
-   Int64  
  
-   UInt64  
  
-   IntPtr  
  
-   Ptr  
  
-   포인터  
  
-   UInptr  
  
-   UPtr  
  
-   UPointer  
  
-   Single  
  
-   Double  
  
-   Decimal  
  
-   GUID  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 **매개 변수에서 발생 한 경우:**  
  
 매개 변수 이름의 데이터 형식 식별자를 더 잘 해당 의미를 설명 하는 단어나 'value' 같은 보다 일반적인 용어로 바꿉니다.  
  
 **발생 한 경우 멤버에 대해:**  
  
 멤버 이름의 언어 특정 데이터 형식 식별자를 더 잘 'value' 같은 보다 일반적인 용어로, 언어 독립 식별자 또는 그 의미를 설명 하는 용어 바꿉니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 형식 기반 매개 변수 및 멤버 이름의 가끔 사용 적합할 수 있습니다. 그러나 알려져 있지 않습니다 새 개발 작업에이 규칙에서 경고를 표시 해야 하는 시나리오가 발생 합니다. 이 있는 이전 배송 라이브러리,이 규칙에서 경고를 표시 해야 할 수 있습니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다.](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)