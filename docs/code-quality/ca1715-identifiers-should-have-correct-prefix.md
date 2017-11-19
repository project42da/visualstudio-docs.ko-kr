---
title: ": Ca1715 식별자에는 올바른 접두사 사용 해야 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8e16e5cf4049ed2bf813cad20fa1be16f8f95dd8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectPrefix|  
|CheckId|CA1715|  
|범주|Microsoft.Naming|  
|변경 수준|주요-인터페이스에서 발생 한 경우입니다.<br /><br /> 주요 변경 아님-제네릭 형식 매개 변수에서 발생 한 경우|  
  
## <a name="cause"></a>원인  
 외부에 표시 되는 인터페이스의 이름이 대문자 "I'로 시작 하지 않습니다.  
  
 또는  
  
 에 외부에서 볼 수 있는 형식 또는 메서드의 제네릭 형식 매개 변수 이름을 않습니다 앞 하지 대문자 ' T '입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 규칙에 따라 특정 프로그래밍 요소의 이름이 특정 접두사로 시작 합니다.  
  
 인터페이스 이름은 대문자에 다른 대 문자가 뒤에 'I'로 시작 해야 합니다. 이 규칙 'MyInterface', 'IsolatedInterface'와 같이 인터페이스 이름에 대 한 위반을 보고합니다.  
  
 제네릭 형식 매개 변수 이름으로 시작 해야 대문자 ' T ' 및 필요에 따라 다른 대문자가 올 수 있습니다. 이 규칙은 'V' 및 'Type'와 같은 제네릭 형식 매개 변수 이름에 대 한 위반 보고 합니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 식별자 이름을 접두사가 올바르게 추가.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 **다음 예제에서는 이름이 잘못 된 인터페이스를 보여 줍니다.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]  
  
## <a name="example"></a>예제  
 **다음 예제에서는 'i'는 인터페이스를 접두사로 사용 하 여 위반을 해결 합니다.**  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]  
  
## <a name="example"></a>예제  
 **다음 예제는 이름이 잘못 제네릭 형식 매개 변수를 보여 줍니다.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]  
  
## <a name="example"></a>예제  
 **다음 예제에서는 앞에 ' T 제네릭 형식 매개 변수를 추가 하 여 위반을 해결 '.**  
  
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1722: 식별자에는 올바른 접두사를 사용해야 합니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)