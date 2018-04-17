---
title: '방법: PolicyActivity 규칙 집합 (레거시) 만들기 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4911912aa46f5dc8a6aea9b9b20e87c1f83e576f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>방법: PolicyActivity 규칙 집합 만들기(레거시)

이 항목을 대상으로 하는 레거시 Windows 워크플로 디자이너를 사용 하 여 설정한 정책 활동 규칙을 만드는 방법에 설명 된 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]합니다.

 끌어 온 후는 **정책** 활동 항목을는 **도구 상자** 워크플로 디자인 화면을 할 새 규칙에 대 한 집합을 만들거나 기존 규칙 선택은 [PolicyActivity ](http://go.microsoft.com/fwlink?LinkID=65019) 활동입니다. 사용 하 여 설정 합니다. 기존 규칙을 선택 된 [선택 규칙 설정 대화 상자 (레거시)](../workflow-designer/select-rule-set-dialog-box-legacy.md) 하 고 사용 하 여 규칙 집합을 만들면는 [규칙 집합 편집기 대화 상자 (레거시)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)합니다.

> [!NOTE]
> 열 수는 [규칙 집합 편집기 대화 상자 (레거시)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) 대화 상자에서 두 번 클릭 하 여 직접는 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) 워크플로 디자인 화면에는 작업입니다.

### <a name="to-select-or-create-a-rule-set-for-a-policyactivity-activity"></a>PolicyActivity 활동의 규칙 집합을 선택하거나 만들려면

1.  마우스 오른쪽 단추로 클릭는 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019), 클릭 하 고 **속성** 열려는 **속성** 창.

2.  클릭는 **RuleSetReference** 속성입니다.

3.  다음 작업 중 하나를 수행합니다.

    -   클릭는 **RuleSetReference** 줄임표 **[...]** , 다음에서 설정 하는 기존 규칙을 선택 하 고는 [선택 규칙 설정 대화 상자 (레거시)](../workflow-designer/select-rule-set-dialog-box-legacy.md)합니다. 10단계로 이동합니다.

         또는

    -   규칙 집합의 이름을 입력합니다. 클릭는 **RuleSetReference** 줄임표 **[...]** 를 선택한 후 **편집** 에 [선택 규칙 설정 대화 상자 (레거시)](../workflow-designer/select-rule-set-dialog-box-legacy.md)합니다.

         -또는-

    -   규칙 집합의 이름을 입력합니다. 확장 된 **RuleSetReference** 속성과 선택 줄임표 **[...]**  에 **RuleSet Definition** 속성입니다.

         [규칙 집합 편집기 대화 상자 (레거시)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) 열립니다.

4.  에 [규칙 집합 편집기 대화 상자 (레거시)](../workflow-designer/rule-set-editor-dialog-box-legacy.md), 클릭 **규칙 추가** 새 규칙 규칙 집합을 추가 하려면.

5.  입력는 **이름**, **우선 순위**, 및 **재평가** 속성, 또는 기본값을 유지 합니다.

6.  입력에 대 한 텍스트는 **조건**합니다.

7.  입력에 대 한 텍스트는 **Thenactions** 및 **Else 작업**합니다.

8.  클릭 **규칙 추가** 다른 규칙을 추가 하려면 다시 합니다.

9. 작업을 마쳤으면 **확인**을 클릭합니다.

## <a name="see-also"></a>참고자료

- [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)
- [규칙 집합 선택 대화 상자(레거시)](../workflow-designer/select-rule-set-dialog-box-legacy.md)
- [규칙 집합 편집기 대화 상자(레거시)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)
- [정책 작업을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65004)
- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)