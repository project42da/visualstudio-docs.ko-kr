---
title: "연습: 사용자 지정 규칙 집합 구성 및 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 연습"
  - "코드 분석, 규칙 집합"
ms.assetid: 7fe0a4e3-1ce0-4f38-a87a-7d81238ec7cd
caps.latest.revision: 40
caps.handback.revision: 40
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: 사용자 지정 규칙 집합 구성 및 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 클래스 라이브러리에 사용자 지정 *규칙 집합*을 사용하도록 구성된 코드 분석 도구를 사용하는 방법을 보여 줍니다.  솔루션에 대해 지정한 프로젝트 형식과 관련된 규칙을 선택하거나, 레거시 코드에서 큰 영향이 없는 방법으로 해결할 수 있는 문제를 검사하는 등 특정 요구 사항에 맞는 대체 규칙 집합을 선택할 수 있습니다.  어느 경우든 규칙 집합을 사용자 지정하여 프로젝트 요구 사항에 맞게 세부적으로 조정할 수도 있습니다.  
  
 이 연습에서는 다음 과정을 단계별로 설명합니다.  
  
-   클래스 라이브러리를 만듭니다.  
  
-   **Microsoft 기본 디자인 지침 규칙** 코드 분석 규칙 집합을 선택합니다.  
  
-   클래스에 사용자 고유의 코드를 추가합니다.  
  
-   코드 분석을 실행합니다.  
  
-   규칙 집합을 사용자 지정합니다.  
  
-   코드 분석을 실행하고 규칙 집합의 사용자 지정 내용이 동작하는 방식을 확인합니다.  
  
## 사전 요구 사항  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## 코드 분석에 규칙 집합 사용  
 먼저 간단한 클래스 라이브러리를 만듭니다.  
  
#### 클래스 라이브러리 만들기  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식**에서 **Visual C\#**을 클릭합니다.  
  
3.  **Visual C\#**에서 **클래스 라이브러리**를 선택합니다.  
  
4.  **이름** 텍스트 상자에 RuleSetSample을 입력한 다음 **확인**을 클릭합니다.  
  
 다음에는 **Microsoft 기본 디자인 지침 규칙** 규칙 집합을 선택하고 이를 프로젝트와 함께 저장합니다.  
  
#### 코드 분석 규칙 집합 선택  
  
1.  **분석** 메뉴에서 **RuleSetSample의 코드 분석 구성**을 클릭합니다.  
  
     코드 분석의 구성 설정이 나타납니다.  
  
2.  **이 규칙 집합 실행** 드롭다운 목록에서 **Microsoft 모든 규칙**을 선택합니다.  
  
     사용 가능한 규칙 집합에 대한 자세한 내용은 [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)을 참조하십시오.  
  
     선택한 규칙 집합과 해당 설정에 대한 정보로 프로젝트 파일을 업데이트하려면 파일 메뉴에서 **선택한 항목 저장**을 클릭합니다.  
  
    > [!TIP]
    >  실제 상황에서 코드 분석을 수행할 문제의 우선 순위를 정하는 좋은 방법은 **최소 권장 규칙** 규칙 집합으로 분석을 시작하여 원하는 문제를 해결한 다음, 규칙 또는 규칙 집합을 점차 추가하여 추가 문제를 찾아 해결하는 것입니다.  
  
 다음에는 CA1704 "식별자에는 정확한 철자를 사용해야 합니다." 코드 분석 규칙의 위반을 보여 주는 데 사용할 클래스 라이브러리에 코드를 추가합니다.  자세한 내용은 [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)을 참조하십시오.  
  
#### 사용자 고유의 코드 추가  
  
-   솔루션 탐색기에서 Class1.cs 파일을 열고 기존 코드를 다음과 같이 바꿉니다.  
  
    ```  
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
  
 이제 RuleSetSample 프로젝트에 대한 코드 분석을 실행하고 오류 목록 창에서 생성된 오류 및 경고를 찾을 수 있습니다.  
  
#### RuleSetSample 프로젝트에 대해 코드 분석 실행  
  
1.  **분석** 메뉴에서 **RuleSetSample에 대해 코드 분석 실행**을 클릭합니다.  
  
2.  오류 목록 창에서 **경고**를 클릭한 다음 **설명** 열 머리글을 클릭하여 경고를 사전순으로 정렬합니다.  
  
     실제 응용 프로그램에서는 이 시점에서 해결할 가치가 있는 규칙 위반을 해결하거나, 해결할 가치가 없는 것으로 확인된 규칙 위반의 경우 선택적으로 규칙을 해제하거나 표시하지 않도록 설정합니다.  자세한 내용은 [SuppressMessage 특성을 사용하여 경고 표시 안 함](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)을 참조하십시오.  
  
3.  CA1704 경고를 살펴봅니다.  이 규칙이 위반되면 "매개 변수에 대해 더 의미 있는 이름을 사용하십시오."라는 메시지가 나타납니다. 코드에서 문제를 해결하거나, 다음 절차에 설명된 대로 규칙을 사용하지 않도록 설정할 수 있습니다.  
  
 다음에는 "식별자에는 정확한 철자를 사용해야 합니다."라는 CA1704 경고를 제외하도록 규칙 집합을 사용자 지정합니다.  
  
#### 프로젝트에 대한 규칙 집합을 사용자 지정하여 특정 규칙을 사용하지 않도록 설정  
  
1.  **분석** 메뉴에서 **RuleSetSample의 코드 분석 구성**을 클릭합니다.  
  
2.  **이 규칙 집합 실행** 드롭다운 목록에서 **Microsoft 모든 규칙** 규칙 집합이 여전히 강조 표시되어 있는지 확인한 다음 **열기**를 클릭합니다.  규칙 집합 페이지가 표시됩니다.  
  
3.  Microsoft.Naming 범주 노드를 확장한 다음 CA1704 경고를 선택합니다.  
  
4.  **동작** 열에서 **없음**을 선택합니다. 이렇게 하면 CA1704가 오류 목록 창에 경고나 오류로 표시되지 않습니다.  
  
     이제 다양한 도구 모음 단추와 필터링 옵션의 사용 방법을 익힐 차례입니다.  예를 들어 **그룹화 방법** 드롭다운 목록을 사용하면 특정 규칙이나 규칙 범주를 쉽게 찾을 수 있습니다.  규칙 집합 페이지 도구 모음의 **사용하지 않는 규칙 숨기기** 단추를 사용하여 **동작** 열이 **없음**으로 설정된 모든 규칙을 숨기거나 표시할 수도 있습니다.  이렇게 하면 해제된 규칙을 검사하여 해당 규칙을 여전히 사용하지 않을지 확인하는 데 유용합니다.  
  
5.  보기 메뉴에서 속성 창을 클릭합니다.  속성 도구 창의 이름 상자에 **My Custom Rule Set**을 입력합니다.  그러면 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] IDE에서 새 규칙 집합의 표시 이름이 변경됩니다.  
  
6.  사용자 지정한 규칙 집합을 저장하기 위해 **파일** 메뉴에서 **Microsoft All Rules.ruleset 저장**을 클릭합니다.  프로젝트의 루트 폴더로 이동합니다.  **파일 이름** 텍스트 상자에 MyCustomRuleSet를 입력합니다.  이제 프로젝트에서 사용할 사용자 지정 규칙 집합을 선택할 수 있습니다.  
  
 새 규칙 집합을 만든 후에는 프로젝트 설정을 구성하여 프로젝트에서 새 규칙 집합을 사용하도록 지정해야 합니다.  
  
#### 프로젝트에서 새 규칙 집합을 사용하도록 지정  
  
1.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **속성** 탭에서 **코드 분석**을 클릭합니다.  
  
     **이 규칙 집합 실행** 드롭다운 목록에서 **\<\<찾아보기...\>\>**를 선택합니다.  코드 프로젝트의 루트 폴더로 이동한 다음 MyCustomRuleSet.ruleset을 선택합니다.  이 규칙 집합은 이전 절차에서 만든 새 규칙 집합입니다.  
  
3.  **파일** 메뉴에서 **저장**을 클릭하여 프로젝트 구성을 저장합니다.  이제 사용자 지정 규칙 집합을 프로젝트에서 사용할 수 있습니다.  
  
 마지막으로, MyCustomRuleSet 규칙 집합을 사용하여 코드 분석을 다시 실행합니다.  이번에는 오류 목록 창에 CA1704 성능 규칙 위반이 표시되지 않습니다.  
  
#### RuleSetSample 프로젝트에 대한 두 번째 코드 분석 실행  
  
1.  **분석** 메뉴에서 **RuleSetSample에 대해 코드 분석 실행**을 클릭합니다.  
  
2.  오류 목록 창에서 **경고**를 클릭해도 "식별자에는 정확한 철자를 사용해야 합니다." 규칙에 대한 CA1704 경고 위반이 더 이상 표시되지 않습니다.  
  
## 참고 항목  
 [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
 [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)