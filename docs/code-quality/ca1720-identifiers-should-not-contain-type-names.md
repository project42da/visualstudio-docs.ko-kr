---
title: "CA1720: 식별자에 형식 이름을 포함하면 안 됩니다. | Microsoft Docs"
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
  - "CA1720"
  - "IdentifiersShouldNotContainTypeNames"
helpviewer_keywords: 
  - "IdentifiersShouldNotContainTypeNames"
  - "CA1720"
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1720: 식별자에 형식 이름을 포함하면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainTypeNames|  
|CheckId|CA1720|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 멤버의 매개 변수 이름에 데이터 형식 이름이 포함되어 있습니다.  
  
 또는  
  
 외부에서 볼 수 있는 멤버의 이름에 언어에 따라 다른 데이터 형식 이름이 포함되어 있습니다.  
  
## 규칙 설명  
 매개 변수 및 멤버의 이름은 개발 도구에서 제공하는 형식을 설명하는 용도보다는 의미를 알려주는 용도로 사용되는 경우가 많습니다.  멤버 이름으로 데이터 형식 이름을 사용해야 하는 경우 언어에 따라 다른 이름 대신 언어에 관계없는 이름을 사용해야 합니다.  예를 들어 C\# 형식 이름인 'int' 대신 언어에 관계없는 데이터 형식 이름인 Int32를 사용합니다.  
  
 매개 변수 또는 멤버 이름의 개별 토큰은 다음과 같은 언어별 데이터 형식 이름과 대\/소문자를 구분하지 않고 비교하여 확인됩니다.  
  
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
  
-   Unsigned  
  
-   Signed  
  
-   Float  
  
-   Float32  
  
-   Float64  
  
 매개 변수 이름은 추가적으로 다음과 같은 언어와 관계없는 데이터 형식 이름과 대\/소문자를 구분하지 않고 비교하여 확인됩니다.  
  
-   Object  
  
-   Obj  
  
-   Boolean  
  
-   Char  
  
-   String  
  
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
  
-   10진수  
  
-   Guid  
  
## 위반 문제를 해결하는 방법  
 **매개 변수에서 발생한 경우:**  
  
 매개 변수 이름의 데이터 형식 식별자를 해당 의미를 보다 잘 설명하는 단어나 'value' 같은 보다 일반적인 단어로 바꿉니다.  
  
 **멤버에서 발생한 경우:**  
  
 멤버 이름의 언어별로 다른 데이터 형식 식별자를 해당 의미를 보다 잘 설명하는 단어, 언어별로 다르지 않은 해당 단어 또는 'value' 같은 보다 일반적인 단어로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 형식 기반 매개 변수 이름 및 멤버 이름을 사용하는 것이 좋은 경우가 있습니다.  그러나, 새로 개발하는 경우 이 규칙에서 경고를 표시하지 않아야 하는 시나리오는 알려져 있지 않습니다.  이전에 제공된 라이브러리의 경우에는 이 규칙에 따른 경고를 표시하지 않아야 할 수 있습니다.  
  
## 관련 규칙  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다.](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)