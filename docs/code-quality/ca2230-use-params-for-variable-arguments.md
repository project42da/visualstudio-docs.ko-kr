---
title: "CA2230: 가변 인수에 대 한 매개 변수를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3bd98c7dd1874617a8f6d6937c56c742a511f0de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: 가변 인수로 params를 사용하십시오.
|||  
|-|-|  
|TypeName|UseParamsForVariableArguments|  
|CheckId|CA2230|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 형식이 사용 하는 public 또는 protected 메서드가 들어는 `VarArgs` 호출 규칙입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 `VarArgs` 가변 개수의 매개 변수를 사용 하는 특정 메서드 정의 호출 규칙이 사용 됩니다. 사용 하는 메서드는 `VarArgs` CLS 규격이 아닙니다. 공용 언어 사양 () 호출 규칙 및 여러 프로그래밍 언어 액세스할 수 없습니다.  
  
 C#에서 `VarArgs` 메서드 매개 변수 목록으로 종료 될 때 호출 규칙이 사용 됩니다는 `__arglist` 키워드입니다. Visual Basic을 지원 하지 않습니다는 `VarArgs` 타원을 사용 하는 관리 되지 않는 코드에만 사용할 수 있습니다 호출 규칙, 및 Visual c + + `...` 표기법입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 C#에서이 규칙 위반을 해결 하려면 사용 된 [params](/dotnet/csharp/language-reference/keywords/params) 키워드 대신 `__arglist`합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 가지 방법, 규칙을 위반 하 고 다른 하나는 규칙을 만족 보여 줍니다.  
  
 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [언어 독립성 및 언어 독립적 구성 요소](/dotnet/standard/language-independence-and-language-independent-components)