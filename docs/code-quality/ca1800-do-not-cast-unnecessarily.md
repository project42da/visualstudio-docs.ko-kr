---
title: "CA1800: 불필요 하 게 캐스팅 하지 마십시오. | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- VB
- CSharp
ms.openlocfilehash: 1d59983639284fb8a6134a73ea58e09c6d49b183
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: 불필요하게 캐스팅하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotCastUnnecessarily|  
|CheckId|CA1800|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
메서드 인수 또는 지역 변수 중 하나에 중복 캐스팅을 수행합니다.

이 규칙에 따라 완벽 하 게 분석에 대 한 테스트 되는 어셈블리 디버깅 정보를 사용 하 여 작성 해야 하 고 관련된 프로그램 데이터베이스 (.pdb) 파일을 사용할 수 있어야 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
중복 캐스팅을 수행하면 성능이 저하됩니다. 특히 간단한 반복 문에서 캐스팅이 수행될 때 더욱 그러합니다. 중복의 명시적 캐스트 작업에 대 한 지역 변수에 캐스팅 결과 저장 하 고 중복 캐스트 작업 대신 지역 변수를 사용 합니다.  
  
경우 C# `is` 실제 캐스팅을 수행 하기 전에 캐스팅이 성공할 지 여부를 테스트 하려면 연산자를 사용 하는 테스트의 결과 `as` 연산자 대신 합니다. 수행 하는 암시적 캐스트 연산 없이 동일한 기능을 제공 된 `is` 연산자입니다. 또는 C# 7.0 이상 버전에서는 사용할는 `is` 연산자와 [패턴 일치](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) 형식 변환 확인 하 고 해당 형식의 변수에 식을 한 번에 캐스팅 합니다.
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 메서드 구현 캐스트 작업의 수를 최소화 하기 위해 수정 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 성능이 중요 하지 않은 경우에이 규칙에서 경고를 표시 하거나 규칙을 완전히 무시 해도 안전를 합니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 C#을 사용 하 여 규칙을 위반 하는 메서드를 보여 줍니다. `is` 연산자입니다. 대체 하 여 규칙을 충족 하는 두 번째 방법은 `is` 연산자의 결과 대 한 테스트로는 `as` 연산자 하나에 두 캐스트 작업 수가 줄어듭니다. 또한 세 번째 방법을 사용 하 여 규칙을 충족 `is` 와 [패턴 일치](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) 형식 변환이 성공 하는 경우 원하는 유형의 변수를 만들거나 합니다.
  
 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]  

 다음 예제에서는 메서드를 `start_Click`, 여러 중복 명시적 캐스팅을 설정 하는, 규칙을 위반 하는 메서드는이 있는 `reset_Click`, 캐스팅을 지역 변수에 저장 하 여 규칙을 만족 하는 합니다.  
  
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
[(C# 참조)](/dotnet/csharp/language-reference/keywords/as)   
[(C# 참조)](/dotnet/csharp/language-reference/keywords/is)