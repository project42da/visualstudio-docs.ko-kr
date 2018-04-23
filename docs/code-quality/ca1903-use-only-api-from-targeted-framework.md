---
title: 'CA1903: 대상 프레임워크에서 API만 사용하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOnlyAPIFromTargetedFramework
- CA1903
helpviewer_keywords:
- UseOnlyApiFromTargetedFramework
- CA1903
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5d8fa2d2580d27e0bdbc45ae0098f432f919eec
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1903-use-only-api-from-targeted-framework"></a>CA1903: 대상 프레임워크에서 API만 사용하십시오.
|||
|-|-|
|TypeName|UseOnlyApiFromTargetedFramework|
|CheckId|CA1903|
|범주|Microsoft.Portability|
|변경 수준|주요-외부에서 볼 수 있는 멤버 또는 형식을 서명에 대해 발생 한 경우입니다.<br /><br /> 주요 변경 아님-메서드의 본문에 발생 한 경우.|

## <a name="cause"></a>원인
 멤버 또는 형식 멤버 또는 프로젝트의 대상된 프레임 워크와 포함 되지 않은 서비스 팩에 도입 된 형식을 사용 합니다.

## <a name="rule-description"></a>규칙 설명
 .NET Framework 2.0 서비스 팩 1 및 2,.NET Framework 3.0 서비스 팩 1과 2 및.NET Framework 3.5 서비스 팩 1에 새 멤버 및 유형이 포함 되어 있습니다. .NET Framework의 주 버전을 대상으로 하는 프로젝트 종속성 이러한 이벤트에 대해 새로운 Api 걸릴 실수로 수 있습니다. 이 종속성을 방지 하려면이 규칙은 모든 새 멤버 및 프로젝트의 대상 프레임 워크를 사용 하 여 기본적으로 포함 되지 않은 형식을 사용 합니다.

 **대상 프레임 워크 및 서비스 팩 종속성**

|||
|-|-|
|대상 프레임 워크|에 도입 된 멤버를 사용할 경우에 발생.|
|.NET Framework 2.0|.NET framework 2.0 SP1,.NET Framework 2.0 SP2|
|.NET Framework 3.0|.NET framework 2.0 SP1,.NET Framework 2.0 s p 2,.NET Framework 3.0 SP1,.NET Framework 3.0 s p 2|
|.NET Framework 3.5|.NET Framework 3.5 SP1|
|.NET Framework 4|N/A|

 프로젝트의 대상 프레임 워크를 변경 하려면 참조 [특정.NET Framework 버전 대상 지정](../ide/targeting-a-specific-dotnet-framework-version.md)합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 서비스 팩에 대 한 종속성을 제거 하려면 형식 또는 새 멤버의 모든 사용을 제거 합니다. 이 의도적인 종속성, 경고를 억제 또는이 규칙을 해제 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 관리 팩은 지정 된 서비스 팩 의도적인 종속성 아닌 경우에이 규칙에서는 경고를에서 표시 하지 마십시오. 이 경우 응용 프로그램이 서비스 팩이 설치 되지 않은 시스템에서 실행 하지 못할 수 있습니다. 경고를 억제 또는 의도적인 종속성이 경우이 규칙을 해제 합니다.

## <a name="example"></a>예제
 다음 예제에서는 DateTimeOffset만.NET 2.0 서비스 팩 1에서 사용할 수 있는 형식을 사용 하는 클래스를 보여 줍니다. 이 예제에서는.NET Framework 2.0가 선택한 프로젝트 속성에 대상 프레임 워크 드롭다운 목록에서 필요 합니다.

 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_1.cs)]

## <a name="example"></a>예제
 다음 예제에서는 앞에서 설명한 위반 DateTimeOffset 형식의 사용 날짜/시간 형식으로 대체 하 여 문제를 해결 합니다.

 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_2.cs)]

## <a name="see-also"></a>참고 항목
 [이식성 경고](../code-quality/portability-warnings.md) [특정.NET Framework 버전 대상 지정](../ide/targeting-a-specific-dotnet-framework-version.md)