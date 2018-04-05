---
title: "연습: 구성 및 사용자 지정을 사용 하 여 규칙 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- code analysis, walkthroughs
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b72a86f10c6e864406929fdccfb59bdd9393752e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="walkthrough-configuring-and-using-a-custom-rule-set"></a>연습: 사용자 지정 규칙 집합 구성 및 사용

이 연습에서는 사용자 지정을 사용 하도록 구성 된 코드 분석 도구를 사용 하는 방법을 보여 줍니다. *규칙 집합* 클래스 라이브러리에 있습니다. 대체 규칙 집합을 특정 요구 사항에 줄 바꿈하지 않는 방법으로 해결할 수 있는 문제에 대 한 레거시 코드를 검사 하는 등, 솔루션에 대해 지정한 하거나 선택할 수 있는 프로젝트 형식에 관련 된 규칙 집합을 선택할 수 있습니다. 두 경우 모두 규칙 집합 또한 사용자 지정할 수 있습니다 프로젝트 요구 사항에를 세부 조정 하도록 합니다.  
  
이 연습에서는 이러한 프로세스를 단계별로 됩니다.  
  
-   클래스 라이브러리를 만듭니다.  
  
-   선택 된 **Microsoft 기본 디자인 지침 규칙** 코드 분석 규칙 집합입니다.  
  
-   클래스에 사용자 고유의 코드를 추가 합니다.  
  
-   코드 분석을 실행 합니다.  
  
-   규칙 집합을 사용자 지정 합니다.  
  
-   코드 분석을 실행 하 고 규칙 사용자 지정 내용이 동작을 설정 하는 방법을 확인 합니다.  
  
## <a name="using-rule-sets-with-code-analysis"></a>에 코드 분석 규칙 집합 사용

먼저 간단한 클래스 라이브러리를 만듭니다.  
  
### <a name="create-a-class-library"></a>클래스 라이브러리 만들기  
  
1.  **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 **프로젝트 형식**, 클릭 **Visual C#**합니다.  
  
3.  아래 **Visual C#**선택, **클래스 라이브러리**합니다.  
  
4.  에 **이름** 텍스트 상자에서 **RuleSetSample** 클릭 하 고 **확인**합니다.  
  
 다음으로, 선택 됩니다는 **Microsoft 기본 디자인 지침 규칙** 규칙 집합을 프로젝트를 저장 합니다.  
  
### <a name="select-a-code-analysis-rule-set"></a>코드 분석 규칙 집합 선택  
  
1.  에 **분석** 메뉴를 클릭 하 여 **RuleSetSample에 대 한 코드 분석 구성**합니다.  
  
     코드 분석에 대 한 구성 설정이 표시 됩니다.  
  
2.  에 **이 규칙 집합 실행** 드롭 다운 목록 **Microsoft 모든 규칙**합니다.  
  
     사용 가능한 규칙 집합에 대 한 자세한 내용은 참조 [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)합니다.  
  
     파일 메뉴에서 클릭 **선택한 항목 저장** 선택한 규칙 집합에 대 한 정보 및 해당 설정을 사용 하 여 프로젝트 파일을 업데이트할 수 있습니다.  
  
    > [!TIP]
    >  실제 상황에서 코드 분석에 대상으로 지정할는 문제를 우선 순위는 것이 좋습니다 시작 하 여이 **최소 권장 규칙** 규칙 집합에서 원하는 문제를 해결 한 단계적으로 추가 규칙 또는 규칙을 찾아 추가 문제 해결을 설정 합니다.  
  
 다음으로 CA1704의 위반을 보여 주기 위해 사용 되는 클래스 라이브러리에 일부 코드를 추가 합니다 "식별자 철자가" 코드 분석 규칙. 자세한 내용은 참조 [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)합니다.  
  
### <a name="add-your-own-code"></a>사용자 고유의 코드를 추가 합니다.  
  
-   솔루션 탐색기에서 Class1.cs 파일 열고 기존 코드를 다음으로 바꿉니다.  
  
    ```csharp
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace RuleSetSample  
    {  
        public class Class1  
        {  
            //The variable parameter names "a" and "b" will cause  
            //the warning CA 1704 Microsoft.Naming "Consider   
            //providing a more meaningful name" to fire  
            public int AddIntegers(int a, int b)  
            {  
  
                int sum = a + b;  
  
                return (sum);  
            }  
        }  
    }
    ```
  
이제 RuleSetSample 프로젝트에서 코드 분석을 실행할 수 있으며 모든 오류 및 오류 목록 창에 생성 된 경고를 검색할 수 있습니다.  
  
### <a name="run-code-analysis-on-the-rulesetsample-project"></a>RuleSetSample 프로젝트에서 코드 분석 실행  
  
1.  에 **분석** 메뉴를 클릭 하 여 **RuleSetSample에서 코드 분석 실행**합니다.  
  
2.  오류 목록 창에서 클릭 **경고** 클릭 하 고는 **설명** 경고를 정렬 하려면 열 머리글 사전순으로 합니다.  
  
     실제 응용 프로그램에서는이 시점에서 수정할 필요가 모든 규칙 위반 문제를 해결 또는 필요에 따라 기능을 해제 하거나 없음을 수정할 필요가 결정 하는 경우 규칙을 표시 하지 않습니다. 자세한 내용은 참조 [경고 표시 안 함](../code-quality/in-source-suppression-overview.md)합니다.
  
3.  CA1704 경고를 확인 합니다. 이 규칙 위반 나타내는 고려해 야 합니다 "는 매개 변수에 대 한 보다 의미 있는 이름을 제공 합니다." 코드에서 문제를 해결 하거나 다음 절차에 설명 된 대로 해당 규칙을 비활성화할 수 있습니다.  
  
 다음으로 규칙 집합 CA1704 경고를 제외 하는 사용자 지정, "식별자 철자가"입니다.  
  
### <a name="customize-the-rule-set-for-your-project-to-disable-a-specific-rule"></a>특정 규칙을 사용 하지 않도록 설정 하려면 프로젝트에 대 한 규칙을 사용자 지정  
  
1.  에 **분석** 메뉴를 클릭 하 여 **RuleSetSample에 대 한 코드 분석 구성**합니다.  
  
2.  **이 규칙 집합 실행** 드롭 다운 목록에서 되어 있는지 확인는 **Microsoft 모든 규칙** 규칙 집합은 여전히 강조 표시 하 고 클릭 **열려**합니다. 규칙 집합 페이지가 표시 됩니다.  
  
3.  Microsoft.Naming 범주 노드를 확장 하 고 CA1704 경고를 선택 합니다.  
  
4.  아래는 **동작** 열에서 선택 **없음.** 이렇게 하면 경고 또는 오류 목록 창에서 오류 표시 안 함 CA1704를 않습니다.  
  
     이제는 것을 다양 한 도구 모음 단추를 사용해이 및 필터링 옵션을 살펴봅니다. 예를 들어, 사용할 수는 **Group By** 특정 규칙 또는 규칙의 범주를 찾기 위해 드롭다운 목록입니다. 사용할 수 있는 또 다른 예로는 **사용 하지 않는 규칙 숨기기** 숨기 거 나 표시 된 모든 규칙 규칙 집합 페이지 도구 모음에서 단추는 **동작** 열으로 설정 **None**합니다. 여전히 되도록 사용 하지 않도록 설정 하도록 확인을 해제 하는 모든 규칙에 대 한 검색 하려는 경우에 유용할 수 있습니다.  
  
5.  보기 메뉴에서 (영문)를 클릭 합니다. 형식 **내 사용자 지정 규칙 집합** 속성 도구 창의 이름 상자에 있습니다. 이렇게 하면 새 규칙 집합의 표시 이름 변경의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] IDE.  
  
6.  에 **파일** 메뉴를 클릭 하 여 **Microsoft 모든 Rules.ruleset 저장** 집합을 사용자 지정된 규칙을 저장 하려면. 프로젝트의 루트 폴더로 이동 합니다. **파일 이름을** 텍스트 상자에서 **MyCustomRuleSet**합니다. 이제 프로젝트와 함께 사용 하기 위해 사용자 지정 규칙 집합을 선택할 수 있습니다.  
  
만든 새 규칙 집합을 지금 설정 된 새 규칙을 사용 하려면를 지정 하도록 프로젝트 설정을 구성 해야 합니다.  
  
### <a name="specify-the-new-rule-set-for-use-with-your-project"></a>프로젝트와 함께 사용 하도록 새 규칙을 지정 합니다.  
  
1.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.  
  
2.  에 **속성** 탭을 클릭 **코드 분석**합니다.  
  
     에 **이 규칙 집합 실행** 드롭 다운 목록에서 클릭  **\<찾아보기... >**합니다. 코드 프로젝트의 루트 폴더로 이동한 다음 선택 **MyCustomRuleSet.ruleset**합니다. 이전 절차에서 만든 새 규칙 집합입니다.  
  
3.  에 **파일** 메뉴에서 클릭 **저장** 프로젝트 구성을 저장 합니다. 이제 사용자 지정 규칙 집합 프로젝트와 함께 사용할 수 있습니다.  
  
 마지막으로, 코드 분석 MyCustomRuleSet 규칙 집합을 사용 하 여 다시 실행 합니다. 알림 오류 목록 창 CA1704 성능 규칙 위반이 표시 되지 않습니다.  
  
### <a name="run-code-analysis-on-the-rulesetsample-project-for-the-second-time"></a>두 번째로 RuleSetSample 프로젝트에서 코드 분석 실행  
  
1.  에 **분석** 메뉴를 클릭 하 여 **RuleSetSample에서 코드 분석 실행**합니다.  
  
2.  오류 목록 창에서 알 수 있듯이 클릭할 때 **경고**, CA1704 경고 위반이 "식별자 철자가" 규칙에 대 한 더 이상 볼 수 없습니다.  
  
## <a name="see-also"></a>참고 항목

[방법: 관리 코드 프로젝트에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
[코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)