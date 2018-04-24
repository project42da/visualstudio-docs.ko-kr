---
title: Visual Studio에서 설정 사용자 지정 코드 분석 규칙 만들기
ms.date: 04/04/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9297d862b0fa47ecc4f5b7b08f6b754e1b5dfc3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="custom-rule-sets"></a>사용자 지정 규칙 집합

사용자 지정을 만들 수 있습니다 *규칙 집합* 코드 분석에 대 한 특정 프로젝트 요구 사항에 맞게 합니다.

## <a name="create-a-custom-rule-set"></a>사용자 지정 규칙 집합 만들기

사용자 지정 규칙 집합을 만들려면, 기본 제공 규칙 집합에 열 수는 **규칙 집합 편집기**합니다. 여기에서 추가 하거나 특정 규칙을 제거할 수 있습니다 및 규칙을 위반 하는 경우 발생 하는 동작을 변경할 수 있습니다&mdash;예를 들어 경고나 오류를 표시 합니다.

1. **솔루션 탐색기**를 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.

2. 에 **속성** 선택 페이지는 **코드 분석** 탭 합니다.

3. 에 **이 규칙 집합 실행** 드롭 다운 목록에서 다음 중 하나를 수행 합니다.

    - 사용자 지정 하려는 규칙 집합을 선택 합니다.

     \- 또는 -

    - 선택  **\<찾아보기... >** 기존 규칙 집합을 지정할 수 없는 목록에 있습니다.

4. 선택 **열려** 규칙 규칙 집합 편집기에 표시를 합니다.

새 규칙 집합 파일을 만들 수도 있습니다는 **새 파일** 대화 상자:

1. 선택 **파일** > **새로** > **파일**, 하거나 키를 눌러 **Ctrl**+**N**.

2. 에 **새 파일** 대화 상자는 **일반** 왼쪽의 범주를 클릭 한 **코드 분석 규칙 집합**합니다.

3. **열기**를 선택합니다.

   새 *.ruleset* 파일이 규칙 집합 편집기에서 열립니다.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>사용자 지정 규칙 집합에서 여러 규칙 집합

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.

2. 에 **속성** 선택 페이지는 **코드 분석** 탭 합니다.

3. 선택  **\<... 관리 여러 규칙 집합 선택 >** 에서 **이 규칙 집합 실행**합니다.

4. 에 **추가 / 제거 규칙 집합** 대화 상자에서 선택 규칙 집합에 포함 시킬 새 규칙 집합입니다.

   ![추가 / 제거 규칙 집합 대화 상자](media/add-remove-rule-sets.png)

5. 선택 **다른 이름으로 저장**에 대 한 이름을 입력 된 *.ruleset* 파일을 선택한 다음 선택 **저장**합니다.

   새 규칙 집합에서 선택 된 **이 규칙 집합 실행** 목록입니다.

6. 선택 **열고** 를 새 규칙 규칙 집합 편집기에 집합을 엽니다.

## <a name="name-and-description"></a>이름 및 설명

편집기에서 열려 있는 규칙 집합의 표시 이름을 변경 하려면 열에서 **속성** 창을 선택 하 여 **보기** > **속성 창** 메뉴 모음에서 합니다. 표시 이름을 입력 된 **이름** 상자입니다. 규칙 집합에 대 한 설명을 입력할 수도 있습니다.

## <a name="next-steps"></a>다음 단계

규칙 집합을 규칙을 추가 또는 규칙을 제거 하거나 규칙 위반의 심각도 수정 하 여 사용자 지정 하는 다음 단계가입니다.

> [!div class="nextstepaction"]
> [규칙 집합 편집기에서 규칙을 수정](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>참고자료

- [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [코드 분석 규칙 집합 참조](../code-quality/rule-set-reference.md)