---
title: "CA1014: CLSCompliantAttribute로 어셈블리 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a870721f0bf7192b417d2105635c663fb69713c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: CLSCompliantAttribute로 어셈블리 표시
|||  
|-|-|  
|TypeName|MarkAssembliesWithClsCompliant|  
|CheckId|CA1014|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 어셈블리에 없는 <xref:System.CLSCompliantAttribute?displayProperty=fullName> 특성이 적용 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 CLS(공용 언어 사양)는 어셈블리가 여러 프로그래밍 언어에 사용될 경우 준수해야 하는 명명 제한, 데이터 형식 및 규칙을 정의합니다. 모든 어셈블리와 CLS 규격을 명시적으로 나타내는 것이 좋습니다 <xref:System.CLSCompliantAttribute>합니다. 특성이 어셈블리에 없으면 해당 어셈블리는 규격입니다.  
  
 CLS 규격 어셈블리의 형식을 포함 하거나 호환 되지 않는 멤버를 입력 하는 것이 불가능 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 합니다. 비규격으로 전체 어셈블리를 표시 하는 대신 형식이 나 형식 멤버를 준수 하지 않는 하 고 이들이 요소 표시를 결정 해야 합니다. 가능 하면 많은 어셈블리의 모든 기능에 액세스할 수 있도록 비규격 멤버에 대해 CLS 규격 대체 항목을 제공 해야 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 어셈블리를 준수 하도록 하지 않으려면 특성을 적용 하 고으로 값을 설정 `false`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리를는 <xref:System.CLSCompliantAttribute?displayProperty=fullName> CLS 규격 선언 하는 특성이 적용 합니다.  
  
 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.CLSCompliantAttribute?displayProperty=fullName>   
 [언어 독립성 및 언어 독립적 구성 요소](http://msdn.microsoft.com/Library/4f0b77d0-4844-464f-af73-6e06bedeafc6)