---
title: "CA1026: 기본 매개 변수를 사용할 수 해야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d7a850c959787282cdf6f9d24b392ef4684b7dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: 기본 매개 변수를 사용하면 안 됩니다.
|||  
|-|-|  
|TypeName|DefaultParametersShouldNotBeUsed|  
|CheckId|CA1026|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 형식이 기본 매개 변수를 사용 하는 외부에서 볼 수 메서드를 포함 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 기본 매개 변수를 사용 하는 메서드를 사용할 수에서 CLS 공용 언어 사양 (); 그러나 CLS 허용 컴파일러에서이 매개 변수에 할당 된 값을 무시 합니다. 기본 매개 변수 값을 무시 하는 컴파일러에 대 한 작성 된 코드는 각 기본 매개 변수에 대 한 인수를 명시적으로 제공 해야 합니다. 여러 프로그래밍 언어에서 원하는 동작을 유지 하려면 기본 매개 변수를 사용 하는 메서드를 기본 매개 변수를 제공 하는 메서드 오버 로드로 바꿔야 합니다.  
  
 관리 코드에 액세스할 때 컴파일러는 기본 매개 변수 값의 관리 되는 확장에 대 한 c + +에 대 한 무시 합니다. Visual Basic 컴파일러를 사용 하는 기본 매개 변수가 있는 메서드를 지원는 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional) 키워드입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 기본 매개 변수를 지정 하는 메서드 오버 로드 된 기본 매개 변수를 사용 하는 메서드를 바꿉니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이와 동일한 기능을 제공 하는 오버 로드 된 메서드와 기본 매개 변수를 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1025: 반복 인수를 매개 변수 배열로 바꾸십시오.](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)  
  
## <a name="see-also"></a>참고 항목  
 [언어 독립성 및 언어 독립적 구성 요소](http://msdn.microsoft.com/Library/4f0b77d0-4844-464f-af73-6e06bedeafc6)