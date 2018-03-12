---
title: "FinalState 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a5b9b8cc1fc0bdb390e1bf32a6a8f262b435a157
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="finalstate-activity-designer"></a>FinalState 활동 디자이너
<xref:System.Activities.Core.Presentation.FinalState> 디자이너는 상태 시스템 인스턴스를 종료하는 <xref:System.Activities.Statements.State>를 만드는 데 사용됩니다.

## <a name="using-the-finalstate-activity-designer"></a>FinalState 활동 디자이너 사용
 **FinalState** 디자이너를 만드는 데 사용 되는 <xref:System.Activities.Statements.State> 하는 상태 시스템에서 종료 상태로 미리 구성 합니다. A <xref:System.Activities.Statements.State> 사용 하 여 만들어진는 <xref:System.Activities.Core.Presentation.FinalState> 활동 디자이너에는 해당 <xref:System.Activities.Statements.State.IsFinal%2A> 속성이로 설정 **true**, 아무런 <xref:System.Activities.Statements.State.Exit%2A> 활동과에서 발생 되는 전환이 없는 합니다. 사용 하는 <xref:System.Activities.Core.Presentation.FinalState> 추가 위한 활동 디자이너는 <xref:System.Activities.Statements.State> 상태 시스템에서 종료 상태로 미리 구성 된 활동으로 끌어는 **FinalState** 활동 디자이너를는 **상태 시스템**의 섹션은 **도구 상자** 워크플로 디자이너에 끌어 놓습니다. <xref:System.Activities.Core.Presentation.FinalState> 활동 디자이너를 <xref:System.Activities.Statements.StateMachine>에 끌어 놓고 나중에 전환을 추가하거나 <xref:System.Activities.Core.Presentation.FinalState> 활동 디자이너를 끌어 놓을 때 전환을 만들 수 있습니다. 전환 만들기에 대 한 자세한 내용은 참조 하십시오. [전환](../workflow-designer/transition-activity-designer.md)합니다.

### <a name="state-activity-properties-in-the-workflow-designer"></a>워크플로 디자이너의 State 활동 속성
 다음 표에서는 <xref:System.Activities.Core.Presentation.FinalState> 디자이너를 사용하여 설정할 수 있는 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다. 이러한 일부 속성은 속성 표에서 편집할 수 있으며 일부 속성은 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.State> 활동 디자이너의 이름을 지정합니다. 기본값은 **상태**합니다. 속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다. <xref:System.Activities.Statements.State.DisplayName%2A>은 Workflow Designer 상단에 표시되는 이동 경로 탐색에 사용됩니다.<br /><br /> <xref:System.Activities.Statements.State.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.State.Entry%2A>|False|이 상태가 전환될 때 발생하는 동작을 지정합니다. 활동을 끌어이 값을 설정할 수 있습니다는 **도구 상자** 놓으면는 <xref:System.Activities.Statements.State.Entry%2A> 상태 섹션.|

## <a name="see-also"></a>참고 항목

- [StateMachine](../workflow-designer/statemachine-activity-designer.md)
- [상태](../workflow-designer/state-activity-designer.md)
- [전환](../workflow-designer/transition-activity-designer.md)