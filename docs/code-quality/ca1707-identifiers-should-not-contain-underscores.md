---
title: ": 식별자 ca1707 밑줄 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 437085b76e1f9595c6db70fce798942df85a0292
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707: 식별자에는 밑줄을 사용할 수 없습니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경-어셈블리에서 발생 한 경우<br /><br /> 아님-형식 매개 변수에서 발생 한 경우|  
  
## <a name="cause"></a>원인  
 식별자의 이름에 밑줄 (_) 문자를 포함합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 규칙에 따라 식별자 이름에는 밑줄 문자(_)가 포함될 수 없습니다. 규칙 네임 스페이스, 형식, 멤버 및 매개 변수를 확인합니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이름에서 밑줄 문자를 모두 제거 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)