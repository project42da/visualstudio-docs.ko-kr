---
title: 'CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b621306bab673172c1c437ca0a959e4bc36f6da
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.
|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 메서드는 문자열 리터럴을 전달 매개 변수로 생성자 또는 메서드에에 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리 및는 문자열은 지역화 될 수 있어야 합니다.

 이 경고는 리터럴 문자열은 매개 변수 또는 속성에 값으로 전달 되며 다음과 같은 경우 중 하나 이상이 true 때 발생 합니다.

-   <xref:System.ComponentModel.LocalizableAttribute> 매개 변수 또는 속성의 특성은 설정을 true로 합니다.

-   "Text", "Message" 또는 "캡션" 매개 변수 또는 속성 이름에 포함 되어 있습니다.

-   Console.Write 또는 Console.WriteLine 메서드에 전달 되는 문자열 매개 변수 이름이 "value" 또는 "format"입니다.

## <a name="rule-description"></a>규칙 설명
 소스 코드에 포함 된 문자열 리터럴을 지역화 하기 어렵습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 리터럴 문자열의 인스턴스를 통해 검색 된 문자열이으로 대체는 <xref:System.Resources.ResourceManager> 클래스입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 코드 라이브러리 지역화 되지 않는 경우 또는 문자열 최종 사용자 또는 코드 라이브러리를 사용 하는 개발자에 노출 되지 않으면이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

 사용자가 메서드에 전달할 수 없습니다. 지역화 된 문자열 매개 변수 또는 명명 된 속성의 이름을 바꾸거나 또는 이러한 항목을 조건부로 표시 하 여를 제거할 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는 범위를 벗어났습니다. 해당 두 인수 중 하나의 경우 예외를 throw 하는 메서드를 보여 줍니다. 첫 번째 인수에 대 한 예외 생성자에는이 규칙을 위반 하는 리터럴 문자열을 전달 됩니다. 두 번째 인수에 대 한 생성자를 통해 검색 된 문자열이 전달 올바르게 됩니다는 <xref:System.Resources.ResourceManager>합니다.

 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>참고 항목
 [데스크톱 앱의 리소스](/dotnet/framework/resources/index)