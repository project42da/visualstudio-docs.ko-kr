---
title: Visual Studio에서 코드 분석 규칙 집합
ms.date: 04/02/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a445aecdd5a9f02bca8d43e42646c991742a626
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>코드 분석 규칙 그룹화를 사용 하 여 규칙 집합

Visual Studio에서 코드 분석을 구성할 때의 기본 제공 목록에서 선택할 수 있습니다 *규칙 집합*합니다. 규칙 집합을 프로젝트에 적용 되며 코드의 그룹을 대상으로 지정 된 문제 및 해당 프로젝트에 대 한 특정 조건을 식별 하는 분석 규칙은. 예를 들어 공개적으로 사용할 수 있는 Api에 대 한 코드를 검색 하도록 디자인 된 규칙 집합을 적용할 수 있습니다 또는 최소 권장 규칙입니다. 또한 모든 규칙을 포함 하는 규칙 집합을 적용할 수 있습니다.

규칙 집합 추가 또는 규칙을 삭제 하거나 규칙 심각도 변경 하 여 경고 또는 오류에서 전자 메일을 사용자 지정할 수 있습니다는 **오류 목록**합니다. 사용자 지정 된 규칙 집합에는 특정 개발 환경의 요구 사항을 충족할 수 있습니다. 규칙 집합을 사용자 지정 규칙 집합 편집기는 검색 및 필터링 하는 프로세스의 도구를 제공 합니다.

## <a name="rule-set-format"></a>규칙 집합 형식

규칙 집합에 XML 형식에 지정 된 한 *.ruleset* 파일입니다. ID로 구성 되는 규칙 및 *작업*, 파일에서 네임 스페이스 및 분석기 ID로 그룹화 됩니다.

XML 콘텐츠는 *.ruleset* 파일 다음과 비슷합니다.

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> 쉽습니다 [규칙 집합 편집](../code-quality/working-in-the-code-analysis-rule-set-editor.md) 그래픽에 **규칙 집합 편집기** 직접 보다 합니다.

규칙 집합에서 지정 된 프로젝트에 대 한는 `CodeAnalysisRuleSet` Visual Studio 프로젝트 파일에서 속성입니다. 예를 들어:

```xml
<CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
```

## <a name="see-also"></a>참고자료

- [코드 분석 규칙 집합 참조](../code-quality/rule-set-reference.md)
