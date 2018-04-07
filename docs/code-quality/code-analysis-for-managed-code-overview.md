---
title: Visual Studio에서 관리 되는 코드에 대 한 분석 코드 | Microsoft Docs
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6d654cb3a7f0d0e952b447337603718c20eaee3e
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2018
---
# <a name="overview-of-code-analysis-for-managed-code"></a>관리 코드에 대 한 코드 분석 개요

Visual Studio 2017 두 가지 방법으로 관리 되는 코드 분석: 이전 *FxCop* .NET 컴파일러 플랫폼 및 관리 되는 어셈블리의 정적 분석 *분석기*합니다. 이 항목에서는 FxCop 정적 코드 분석에 설명 합니다. .NET 컴파일러 플랫폼 분석기를 사용 하 여 코드를 분석 하는 방법에 대 한 자세한 참조 [Roslyn 개요 분석기](../code-quality/roslyn-analyzers-overview.md)합니다.

관리 코드에 대한 코드 분석에서는 관리되는 어셈블리를 분석하고, Microsoft .NET Framework 디자인 지침에 설정된 프로그래밍 및 디자인 규칙의 위반과 같은 어셈블리 관련 정보를 보고합니다.

분석 도구는 분석하는 동안 수행하는 검사를 경고 메시지로 나타냅니다. 경고 메시지는 관련 프로그래밍 및 디자인 문제를 식별하며 가능한 경우 문제 해결 방법에 대한 정보를 제공합니다.

## <a name="ide-integrated-development-environment-integration"></a>IDE (통합된 개발 환경) 통합

수동 또는 자동으로 프로젝트에서 코드 분석을 실행할 수 있습니다.

프로젝트를 빌드할 때마다 코드 분석을 실행 하려면 선택 **빌드에 코드 분석 사용** 프로젝트의 속성 페이지에 있습니다. 자세한 내용은 참조 [하는 방법: 설정 및 자동 코드 분석 사용 안 함](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)합니다.

프로젝트에 대해 수동으로 코드 분석을 실행 하려면 선택에 메뉴 모음에서 **분석** > **코드 분석 실행** > **에서 코드 분석 실행 \<프로젝트 >**합니다.

## <a name="rule-sets"></a>규칙 집합

으로 관리 되는 코드에 대 한 코드 분석 규칙 그룹화 됩니다 [규칙 집합](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)합니다. Microsoft 표준 규칙 집합 중 하나를 사용 하거나 할 수 있습니다 [사용자 지정 규칙 집합 만들기](../code-quality/how-to-create-a-custom-rule-set.md) 특정 요구 사항에 하 합니다.

## <a name="suppress-warnings"></a>경고 표시 안 함

경고가 적용되지 않는 것으로 표시하면 유용한 경우가 많습니다. 이렇게 하면 경고를 조사한 다음 이를 표시하지 않거나 무시하도록 설정했다는 것을 개발자와 나중에 이 코드를 검토할 수 있는 다른 사람에게 알릴 수 있습니다.

경고의 소스에서 억제 (suppression)는 사용자 지정 특성을 통해 구현 됩니다. 경고를 표시하지 않으려면 다음 예제와 같이 소스 코드에 `SuppressMessage` 특성을 추가합니다.

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

자세한 내용은 참조 [경고 표시 안 함](../code-quality/in-source-suppression-overview.md)합니다.

> [!NOTE]
> Visual Studio 2017로 프로젝트를 마이그레이션하는 경우 많은 수의 코드 분석 경고에 직면할 갑자기 수 있습니다. 경고를 수정 하 고 생산성을 높이려는 즉시 준비 하지 않은 경우 다음을 할 수 있습니다 *초기* 프로젝트의 분석 상태입니다. **분석** 메뉴 선택 **코드 분석 실행 하 고 활성 문제를 표시 하지 않는**합니다.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 코드 분석 실행

조직에서 반드시 특정 정책에 따라 체크 인을 수행하려는 경우 특히 다음 정책을 따르는지 확인할 수 있습니다.

- 코드 체크 인 중에 빌드 오류가 있습니다.

- 가장 최근 빌드의 일부로 코드 분석을 실행 합니다.

체크 인 정책을 지정하여 위 사항을 확인할 수 있습니다. 자세한 내용은 참조 [팀 프로젝트 체크 인 정책 사용 하 여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)합니다.

## <a name="team-build-integration"></a>팀 빌드 통합

빌드 시스템의 통합된 기능을 사용하여 빌드 프로세스의 일부로 분석 도구를 실행할 수 있습니다. 자세한 내용은 참조 [빌드 및 릴리스 (VSTS)](/vsts/build-release/index)합니다.

## <a name="see-also"></a>참고자료

- [Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [방법: 자동 코드 분석 활성화 및 비활성화](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
