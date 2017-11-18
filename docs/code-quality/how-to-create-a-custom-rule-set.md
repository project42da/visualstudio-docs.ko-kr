---
title: "방법: 사용자 지정 규칙 집합 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.addremoverulesets
helpviewer_keywords: Development Edition, rule sets
ms.assetid: bcc42508-9592-4802-9f66-a50111641d73
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e9cba33565af81a76d043a3fc3f63eef831e1ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-custom-rule-set"></a>방법: 사용자 지정 규칙 집합 만들기
[!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)], [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)], 및 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]를 만들고 사용자 지정을 수정할 수 *규칙 집합* 코드 분석와 관련 된 특정 프로젝트 요구 사항에 맞게 합니다. 사용자 지정 규칙 집합을 만들려면, 또는 하나를 더 표준 규칙 규칙 집합 편집기에 설정 합니다. 다음 추가 하거나 특정 규칙을 제거할 수 있으며 코드 분석 규칙 위반을 판단 하는 경우 발생 하는 동작을 변경할 수 있습니다.  
  
 새 사용자 지정 규칙 집합을 만들려면, 새 파일 이름을 사용 하 여 저장 합니다. 사용자 지정 규칙 집합을 프로젝트에 자동으로 할당 됩니다.  
  
## <a name="opening-the-rule-set-editor"></a>열 규칙 집합 편집기  
  
#### <a name="to-open-an-empty-rule-set-file-in-the-rule-set-editor"></a>규칙 집합 편집기에서 규칙 집합 파일 빈을 열려면  
  
1.  에 **파일** 의 메뉴 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], 가리킨 **새로** 클릭 하 고 **파일**합니다.  
  
2.  에 **새 파일** 대화 상자를 클릭 **일반** 에 **설치 된 템플릿** 목록에서 선택한 후 **코드 분석 규칙 집합**합니다.  
  
3.  규칙 집합 편집기가 나타납니다. 규칙은 편집기 목록에서 선택 됩니다.  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>단일 기존 규칙 집합에서 사용자 지정 규칙을 만들려면  
  
1.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.  
  
2.  에 **속성** 탭을 클릭 **코드 분석**합니다.  
  
3.  에 **규칙 집합** 드롭 다운 목록에서 다음 중 하나를 수행 합니다.  
  
    -   사용자 지정 하려는 규칙 집합을 선택 합니다.  
  
     \- 또는 -  
  
    -   선택  **\<찾아보기... >** 기존 규칙 집합을 지정할 수 없는 목록에 있습니다.  
  
4.  클릭 **열려** 규칙 규칙 집합 편집기에 표시를 합니다.  
  
#### <a name="to-create-a-custom-rule-set-from-multiple-existing-rule-sets"></a>여러 기존 규칙 집합에서 집합을 사용자 지정 규칙을 만들려면  
  
1.  솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.  
  
2.  에 **속성** 탭을 클릭 **코드 분석**합니다.  
  
3.  선택  **\<... 관리 여러 규칙 집합 선택 >** 에서 **이 규칙 집합 실행**합니다.  
  
4.  에 **추가 / 제거 규칙 집합** 대화 상자에서 규칙 집합에 새 규칙 집합 기반 하 고 클릭 하려는 **확인**합니다.  
  
5.  새 규칙 집합을 저장 합니다.  
  
     새 규칙 집합의 이름이 선택 되는 **이 규칙 집합 실행** 목록입니다. 다음 단계에서 규칙 집합의 표시 이름을 변경할 수 있습니다.  
  
6.  (선택 사항) 규칙 집합의 표시 이름을 변경 하려면는 **보기** 메뉴를 클릭 하 여 **속성 창**합니다. 표시 이름을 입력 된 **이름** 상자입니다.  
  
7.  하려면 추가, 제거 또는 새 규칙 집합의 특정 코드 분석 규칙을 수정을 클릭 **열려**합니다.  
  
## <a name="modifying-a-rule-set"></a>규칙 집합 수정  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>규칙을 수정 하려면 규칙 집합 편집기에서 설정  
  
-   규칙 집합의 표시 이름을 변경 하려면는 **보기** 메뉴를 클릭 하 여 **속성 창**합니다. 표시 이름을 입력 된 **이름** 상자입니다. 표시 이름은 파일 이름에서 달라질 수 있음을 확인 합니다.  
  
-   그룹의 모든 규칙을 사용자 지정 규칙 집합을 추가 하려면 그룹의 확인란을 선택 합니다. 그룹의 모든 규칙을 제거 하려면 확인란의 선택을 취소 합니다.  
  
-   특정 규칙을 사용자 지정 규칙 집합을 추가 하려면 규칙의 확인란을 선택 합니다. 규칙 집합에서 규칙을 제거 하려면 확인란의 선택을 취소 합니다.  
  
-   코드 분석에서 규칙을 위반 하는 경우 수행할 작업을 변경 하려면 클릭는 **동작** 규칙에 대 한 필드를 다음 값 중 하나를 선택 합니다.  
  
     **경고** -경고를 생성 합니다.  
  
     **오류** -오류가 발생 합니다.  
  
     **None** -규칙을 비활성화 합니다. 이 동작은 규칙 규칙 집합에서 제거 하는 동일 합니다.  
  
## <a name="changing-the-rule-set-editor-display"></a>편집기 표시를 설정 하는 규칙을 변경 합니다.  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>그룹을 필터링 하거나 규칙 집합 편집기 도구 모음을 사용 하 여 규칙 집합 편집기에서 필드를 변경 합니다.  
  
-   모든 그룹의 규칙을 확장 하려면 **모두 확장**합니다.  
  
-   모든 그룹의 규칙을 축소 하려면 클릭 **모두 축소**합니다.  
  
-   규칙 통해 그룹화 되는 필드를 변경 하려면 필드를 선택는 **Group By** 목록입니다. 그룹 해제 된 규칙을 표시 하려면 선택  **\<없음 >**합니다.  
  
-   를 추가 하거나 규칙 열에 있는 필드를 제거 하려면 클릭 **열 옵션**합니다.  
  
-   현재 솔루션에 적용 되지 않는 규칙을 숨기려면 **현재 솔루션에 적용 되지 않는 규칙 숨기기**합니다.  
  
-   오류 작업이 할당 된 규칙 표시 / 숨김을 전환 하려면 클릭 **코드 분석 오류를 생성할 수 있는 규칙 표시**합니다.  
  
-   경고 작업이 할당 된 규칙 표시 / 숨김을 전환 하려면 클릭 **코드 분석 경고를 생성할 수 있는 규칙 표시**합니다.  
  
-   할당 된 규칙 표시 / 숨김을 전환 하려면는 **None** 동작을 클릭 하 여 **활성화 되지 않는 규칙 표시**합니다.  
  
-   를 추가 하거나 Microsoft 기본 규칙 집합을 현재 규칙 집합을 제거 하려면 클릭 **자식 규칙 집합 추가 또는 제거**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 관리 코드 프로젝트에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
 [코드 분석 규칙 집합 참조](../code-quality/code-analysis-rule-set-reference.md)