---
title: ": 식별자 ca1716 키워드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 619fc7867d14a26f2c3b674b4b8ac8b2d8fba114
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: 식별자는 키워드와 달라야 합니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldNotMatchKeywords|  
|CheckId|CA1716|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 네임 스페이스, 형식, 또는 가상 또는 인터페이스 멤버의 이름에는 프로그래밍 언어의 예약된 키워드와 일치 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 네임 스페이스, 형식에 대 한 식별자 및 가상 하며 인터페이스 멤버는 공용 언어 런타임을 대상으로 하는 언어에서 정의 된 키워드와 일치 하지 해야 합니다. 사용 되는 언어와 키워드에 따라 컴파일러 오류 및 모호성이 라이브러리를 사용 하 여 어려워질 수 있습니다.  
  
 이 규칙은 다음 언어의 키워드를 확인 합니다.  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 대/소문자 비구분 비교에 사용 되 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 키워드 및 대/소문자 구분 비교 다른 언어에 사용 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 키워드의 목록에 표시 되지 않는 이름을 선택 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 식별자 API, 사용자가 혼동 하지는 없으며 라이브러리에서 사용 가능한 모든 언어에서 사용할 수는 확신 하는 경우이 규칙에서는 경고를에서 표시 하지 않을 수 있습니다는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.