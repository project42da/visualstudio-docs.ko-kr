---
title: '방법: 선언적 규칙 조건 (레거시) 만들기 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e8b1d1220f11d27ee193e3e82168f4c10558d86
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>방법: 선언적 규칙 조건 만들기(레거시)
이 항목에서는 대상으로 하는 레거시 Windows 워크플로 디자이너를 사용 하 여 규칙 조건을 선언 하는 방법을 설명는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]합니다.

 조건 문으로 계산 **True** 또는 **False**합니다. 선언적 규칙 조건을 사용 하 여 만든 조건문은는 [규칙 조건 편집기 대화 상자 (레거시)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md) 워크플로와 함께 XML로 저장 합니다. 여러 조건자를 결합하는 부울 대수와 워크플로 상태를 비교하는 조건자가 포함될 수 있습니다.

 선언적 규칙 조건은 기본적으로 제공되는 다음과 같은 Windows Workflow Foundation 활동에 사용됩니다.

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

### <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>규칙 조건 편집기를 사용하여 선언적 규칙 조건을 만들려면

1.  활동의에서 **속성** 창 클릭는 **조건** 속성 또는 **UntilCondition** 활동에 따라 속성입니다.

2.  선택 **선언적 규칙 조건** 속성에 대 한 목록에서 합니다.

3.  확장 된 **조건** 또는 **UntilCondition** 속성입니다.

4.  클릭는 **ConditionName** 속성입니다.

5.  클릭는 **ConditionName** 줄임표 **[...]**  열려는 **조건 선택** 대화 상자.

6.  클릭 **새 조건** 열려는 **규칙 조건 편집기** 대화 상자.

7.  조건에 식을 입력는 **조건** 입력란.

     조건식을 만드는 방법에 대 한 정보를 참조 하십시오. [규칙 조건 편집기 대화 상자 (레거시)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)합니다.

8.  조건 식 작성이 완료 했으면 클릭 **확인** 대화 상자를 닫고 할당된 된 이름으로 규칙 조건을 만듭니다.

     **조건 선택** 대화 상자가 열립니다.

     사용 하는 방법에 대 한 내용은 **조건 선택** 대화 상자, 참조 [조건 선택 대화 상자 (레거시)](../workflow-designer/select-condition-dialog-box-legacy.md)합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)
- [ConditionedActivityGroup를 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65066)
- [IfElseBranchActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65075)
- [복제기 활동 사용](http://go.microsoft.com/fwlink?LinkID=65080)
- [While을 사용 하 여 활동](http://go.microsoft.com/fwlink?LinkID=65091)
- [규칙 조건 편집기 대화 상자(레거시)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)
- [조건 선택 대화 상자(레거시)](../workflow-designer/select-condition-dialog-box-legacy.md)
- [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)