---
title: Visual Studio에서 Roslyn 분석기
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: f5a434a47bac73aef86e83d220605b196fc2a74a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET 컴파일러 플랫폼 분석기 개요

Visual Studio 2017 입력할 때 C# 또는 Visual Basic 코드를 분석 하는.NET 컴파일러 플랫폼 분석기의 기본 제공 된 집합을 가집니다. NuGet 패키지로 프로젝트별으로 또는 Visual Studio 확장으로 추가 분석기를 설치할 수 있습니다. 분석기 코드 스타일, 코드 품질 및 유지 관리 용이성, 코드 디자인 및 기타 문제를 살펴봅니다.

보고 하는 분석기에서 규칙 위반 발견 되 면 모두으로 코드 편집기에는 *구불구불한* 문제를 일으키는 코드 아래 및는 **오류 목록**합니다.

많은 분석기 규칙 또는 *진단*, 하나 이상의 연결 된 *코드 수정을* 문제를 해결 하려면 적용할 수 있습니다. Visual Studio에 내장 된 분석기 진단 수 있으며, 관련된 코드 수정 코드 수정 다른 종류의 함께 전구 아이콘 메뉴에 표시 되어 *빠른 작업*합니다. 이러한 코드 수정에 대 한 정보를 참조 하십시오. [일반적인 빠른 작업](../ide/common-quick-actions.md)합니다.

![분석기 위반이 발생 하 고 빠른 작업 코드 수정](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>정적 코드 분석 및 Roslyn 분석기

.NET 컴파일러 플랫폼 ("Roslyn") 분석기 대체 [정적 코드 분석](../code-quality/code-analysis-for-managed-code-overview.md) 관리 코드에 대 한 합니다. Roslyn 분석기 진단으로 다시 작성 되었습니다 이미 정적 코드 분석 규칙.

정적 코드 분석 규칙 위반 처럼 Roslyn 분석기 위반에 표시 된 **오류 목록**합니다. 또한 Roslyn 분석기 위반에에서도 표시으로 코드 편집기 *물결 모양* 문제를 일으키는 코드 아래 합니다. 구불구불한는 색에 따라 달라 집니다는 [심각도 설정](../code-quality/use-roslyn-analyzers.md#rule-severity) 규칙의 합니다. 다음 스크린샷은 세 위반&mdash;빨간색 하나, 하나 녹색 및 하나의 회색:

![코드 편집기에서 물결 모양](media/diagnostics-severity-colors.png)

정적 코드 분석을 사용 하지만 또한 입력할 때 live 등의 빌드 시에 코드를 분석 하는 Roslyn 분석기! Roslyn 분석기를 사용 하면 편집기에 열려 되지 않는 코드 파일의 디자인 타임 분석을 제공할 수도 [전체 솔루션 분석이](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)합니다.

> [!NOTE]
> Roslyn 분석기에서 빌드 시 오류 및 경고는에 표시 분석기에서 NuGet 패키지로 설치 됩니다.

Roslyn 분석기 같은 종류의 정적 코드 분석을 수행 하는 문제가 보고 할 뿐 아니라을 쉽게 하나 또는 모두, 파일 또는 프로젝트에서 위반이 발생 횟수를 수정할 수 있도록 합니다. 이러한 작업 이라고 *코드 수정을*합니다. 코드 수정 IDE로 적용 됩니다. Visual Studio에서으로 구현 된 사실을 [빠른 작업](../ide/quick-actions.md)합니다. 일부 분석기 진단 수 있으며, 관련된 코드 수정

> [!NOTE]
> 메뉴 옵션 **분석** > **코드 분석 실행** 에 정적 코드 분석 적용 됩니다. 한 프로젝트에서 또한 **코드 분석** 속성 페이지는 **빌드에 코드 분석 사용** 및 **생성 된 코드 결과 표시 안 함** 확인란에만 적용 정적 코드 분석 합니다. 갖습니다 Roslyn 분석기에 대 한 영향을 주지 않습니다.

Roslyn 분석기에서 위반 및 정적 코드 분석에서 간을 구분 하려면는 **오류 목록**를 살펴보고는 **도구** 열입니다. 도구 값의 분석기 어셈블리 중 하 나와 일치 하는 경우 **솔루션 탐색기**, 예를 들어 **Microsoft.CodeQuality.Analyzers**, 위반 Roslyn 분석기에서 제공 합니다. 그렇지 않으면 위반 정적 코드 분석에서 생성 됩니다.

![오류 목록에 열 도구](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-vs-extension"></a>확장 및 NuGet 패키지

Visual Studio extension NuGet 패키지 또는 Visual Studio 전체를 통해 프로젝트를 설치 하는.NET 컴파일러 플랫폼 분석기 될 수 있습니다. 이러한 두 방법 간의 주요 동작 차이가 있습니다 [분석기 설치](../code-quality/install-roslyn-analyzers.md)합니다.

### <a name="scope"></a>범위

Visual Studio 확장으로 분석기를 설치 하는 경우 적용할 솔루션 수준에서 Visual Studio의 모든 인스턴스. 이 기본 메서드이며 NuGet 패키지로 분석기를 설치 하는 경우 NuGet 패키지가 설치 된 프로젝트에만 적용 됩니다. 팀 환경에서는 NuGet 패키지로 설치 하는 분석기에 대 한 범위에 있는 *모든 개발자가* 해당 프로젝트에서 사용할 수 있는 합니다.

### <a name="build-errors"></a>빌드 오류

한 규칙 적용 (CI) 빌드 명령줄을 통해 또는 연속 통합의 일부로 비롯 한 빌드 시 NuGet 패키지로 분석기를 설치 합니다. 분석기 경고 및 오류가 표시 되지 않는 빌드 보고서에 대 한 확장으로 분석기를 설치 하는 경우.

다음 스크린 샷에서 분석기 규칙 위반을 포함 하는 프로젝트를 빌드 명령줄 빌드 출력을 보여 줍니다.

![규칙 위반을 사용 하 여 MSBuild 출력](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>규칙의 심각도

Visual Studio 확장으로 설치 된 분석기에서 규칙의 심각도 설정할 수 없습니다. 구성 하려면 [심각도 규칙](../code-quality/use-roslyn-analyzers.md#rule-severity), NuGet 패키지로 분석기를 설치 합니다.

## <a name="next-steps"></a>다음 단계

- [Visual Studio에서 Roslyn 분석기를 설치 합니다.](../code-quality/install-roslyn-analyzers.md)
- [Roslyn 분석기를 사용 하 여 Visual Studio에서](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 바로 가기](../ide/quick-actions.md)
- [사용자 고유의 Roslyn 분석기를 작성 합니다.](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET 컴파일러 플랫폼 SDK](/dotnet/csharp/roslyn-sdk/)