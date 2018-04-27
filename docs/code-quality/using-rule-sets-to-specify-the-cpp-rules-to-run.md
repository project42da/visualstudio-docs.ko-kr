---
title: 규칙 집합을 사용하여 실행할 C++ 규칙 지정
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: ccb64fba6a646de0974c9de6e35beb98738b7300
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>규칙 집합을 사용 하 여 실행을 위해 c + + 규칙을 지정 하려면

Visual Studio에서 있습니다 만들고 수정할 수는 사용자 지정 *규칙 집합* 코드 분석와 관련 된 특정 프로젝트 요구 사항에 맞게 합니다. 기본 규칙 집합에 저장 된 `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`합니다.

**Visual Studio 2017 버전 15.7** 만들어 모든 텍스트를 사용 하 여 사용자 지정 규칙 집합 편집기 하는 어떤 빌드 사용 하는 시스템에 관계 없이 빌드 명령줄에서에서이 적용 합니다. 자세한 내용은 참조 [/analyze: ruleset](/cpp/build/reference/analyze-code-quality)합니다.

Visual Studio에서 설정 하는 사용자 지정 c + + 규칙을 만들려면 C/c + + 프로젝트를 Visual Studio IDE에서 열려 있어야 합니다. 그런 다음 규칙 집합 편집기에서 표준 규칙 집합을 열고, 특정 규칙을 추가 또는 제거하고, 필요에 따라 코드 분석으로 규칙이 위반된 것으로 확인될 때 발생하는 작업을 변경합니다.

새 사용자 지정 규칙 집합을 만들려면, 새 파일 이름을 사용 하 여 저장 합니다. 사용자 지정 규칙 집합을 프로젝트에 자동으로 할당 됩니다.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>단일 기존 규칙 집합에서 사용자 지정 규칙을 만들려면

1. 솔루션 탐색기에서 프로젝트에 대 한 바로 가기 메뉴를 열고 선택한 후 **속성**합니다.

2. 에 **속성** 탭에서 선택 **코드 분석**합니다.

3. 에 **규칙 집합** 드롭 다운 목록에서 다음 중 하나를 수행 합니다.

    - 사용자 지정하려는 규칙 집합을 선택합니다.

     \- 또는 -

    - 선택  **\<찾아보기... >** 기존 규칙 집합을 지정할 수 없는 목록에 있습니다.

4. 선택 **열려** 규칙 규칙 집합 편집기에 표시를 합니다.

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>규칙을 수정 하려면 규칙 집합 편집기에서 설정

- 규칙 집합의 표시 이름을 변경 하는 **보기** 메뉴 선택 **속성 창**합니다. 표시 이름을 입력 된 **이름** 상자입니다. 표시 이름은 파일 이름에서 달라질 수 있음을 확인 합니다.

- 그룹의 모든 규칙을 사용자 지정 규칙 집합을 추가 하려면 그룹의 확인란을 선택 합니다. 그룹의 모든 규칙을 제거 하려면 확인란의 선택을 취소 합니다.

- 특정 규칙을 사용자 지정 규칙 집합을 추가 하려면 규칙의 확인란을 선택 합니다. 규칙 집합에서 규칙을 제거 하려면 확인란의 선택을 취소 합니다.

- 코드 분석에서 규칙을 위반 하는 경우 수행 되는 동작을 변경 하려면는 **동작** 규칙에 대 한 필드를 다음 값 중 하나를 선택 합니다.

     **경고** -경고를 생성 합니다.

     **오류** -오류가 발생 합니다.

     **None** -규칙을 비활성화 합니다. 이 동작은 규칙 규칙 집합에서 제거 하는 동일 합니다.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>그룹을 필터링 하거나 규칙 집합 편집기 도구 모음을 사용 하 여 규칙 집합 편집기에서 필드를 변경 합니다.

- 모든 그룹의 규칙을 확장 하려면 **모두 확장**합니다.

- 모든 그룹의 규칙을 축소 하려면 탭 선택 **모두 축소**합니다.

- 규칙 통해 그룹화 되는 필드를 변경 하려면 필드를 선택는 **Group By** 목록입니다. 그룹 해제 된 규칙을 표시 하려면 선택  **\<없음 >** 합니다.

- 를 추가 하거나 규칙 열에 있는 필드를 제거 하려면 선택 **열 옵션**합니다.

- 현재 솔루션에 적용 되지 않는 규칙을 숨기려면 선택 **현재 솔루션에 적용 되지 않는 규칙 숨기기**합니다.

- 오류 작업이 할당 된 규칙 표시 / 숨김을 전환 하려면 **코드 분석 오류를 생성할 수 있는 규칙 표시**합니다.

- 경고 작업이 할당 된 규칙 표시 / 숨김을 전환 하려면 선택 **코드 분석 경고를 생성할 수 있는 규칙 표시**합니다.

- 할당 된 규칙 표시 / 숨김을 전환 하려면는 **None** 동작을 선택 **활성화 되지 않는 규칙 표시**합니다.

- 를 추가 하거나 Microsoft 기본 규칙 집합을 현재 규칙 집합을 제거 하려면 선택 **자식 규칙 집합 추가 또는 제거**합니다.

## <a name="to-create-a-rule-set-in-a-text-editor"></a>텍스트 편집기에서 설정 하는 규칙을 만들려면

편집기에서 텍스트를 사용자 지정 규칙 집합을 만들고, 된 모든 위치에 저장할 수 있습니다는 `.ruleset` 확장을 사용 하 여 적용 하 고는 [/analyze: ruleset](/cpp/build/reference/analyze-code-quality) 컴파일러 옵션입니다.

다음 예제는 시작 점으로 사용할 수 있는 파일을 설정 하는 기본 규칙을 보여 줍니다.

```xml

<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```
