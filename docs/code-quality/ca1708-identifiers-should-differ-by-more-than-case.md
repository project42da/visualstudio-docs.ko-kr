---
title: 'CA1708: 식별자는 대/소문자만 달라 야 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35626f9e59aa1138c6d1756953ed5fdd72906deb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldDifferByMoreThanCase|  
|CheckId|CA1708|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 두 형식, 멤버, 매개 변수 또는 정규화 된 네임 스페이스의 이름을 소문자로 변환 될 경우 동일 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다. 예를 들어 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 는 대/소문자 구분 널리 사용 되는 언어입니다.  
  
 이 규칙은 공개적으로 표시 하는 멤버에만 적용 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 대/소문자 구분 방식으로 다른 식별자에 비교 했을 때 고유 이름을 선택 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 라이브러리에서 사용 가능한 모든 언어에서 사용 하지 못할는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.  
  
## <a name="example-of-a-violation"></a>위반의 예로  
 다음 예제에서는이 규칙 위반을 보여 줍니다.  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)