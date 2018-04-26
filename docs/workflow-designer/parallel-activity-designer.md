---
title: 워크플로 디자이너-Parallel 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2315c27bc0a35ac1dc839b5fd98003105d92bd4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="parallel-activity-designer"></a>Parallel 활동 디자이너

<xref:System.Activities.Statements.Parallel> 활동은 자식 활동 컬렉션을 동시에 실행합니다.

## <a name="the-parallel-activity"></a>Parallel 활동

<xref:System.Activities.Statements.Parallel> 활동은 자식 활동을 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 저장합니다. 일부 자식 활동이 유휴 상태가 될 수 있는 경우에는 <xref:System.Activities.Statements.Parallel> 활동 대신 <xref:System.Activities.Statements.Sequence> 활동을 사용합니다.

<xref:System.Activities.Statements.Parallel> 활동에는 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 는 사용자가 포함 된 속성에는 Visual Basic 식을 지정 합니다. <xref:System.Activities.Statements.Parallel> 활동은 각 분기가 완료된 후 이 속성을 평가합니다. 로 평가 되 면 **True**, 하면 <xref:System.Activities.Statements.Parallel> 활동이 다른 분기를 실행 하지 않고 완료 합니다. 경우는 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 계산 되지 않습니다 **True**, 하면 <xref:System.Activities.Statements.Parallel> 자식 활동이 모두 완료 했을 때 활동이 완료 합니다.

### <a name="using-the-parallel-activity-designer"></a>Parallel 활동 디자이너 사용

**병렬** 활동 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**워크플로 디자이너의 왼쪽에 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

**병렬** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동 디자이너는 일반적으로 안쪽에 배치, 예를 들어 한 때마다워크플로디자이너화면에끌어놓및**시퀀스** 활동 디자이너입니다. 워크플로 디자이너에 놓으면 만듭니다는 <xref:System.Activities.Statements.Parallel> 기본적으로 포함 된 활동을 한 <xref:System.Activities.Activity.DisplayName%2A> 의 **병렬**

에 활동을 추가 하는 <xref:System.Activities.Statements.Parallel.Branches%2A> parallel 활동의 컬렉션에는 몇 가지 다른 활동 디자이너를 끌어는 **도구 상자** 내부에 있는 삼각형에 놓는 것는 **병렬** 활동 디자이너입니다. 이 삼각형은 분기에 포함된 활동 옆에 표시됩니다. 이 절차를 반복하여 다른 활동을 추가할 수 있습니다. 활동 끌어서 놓아 내에서 다시 정렬할 수 있습니다는 **병렬** 활동 디자이너입니다.

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>워크플로 디자이너의 Parallel 활동 속성

다음 표에서는 가장 유용한 Parallel 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다. 기본값은 **병렬**합니다. 값을 선택적으로 편집할 수는 **속성** 표에서 또는 활동 디자이너 머리글에서 직접 합니다.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|실행할 자식 활동의 컬렉션을 포함합니다.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|분기가 완료된 후 확인됩니다. 로 평가 되 면 **True**, 예약 된 보류 중인 분기가 취소 됩니다. 이 속성이 설정 되어 있지 않거나로 평가 되는 경우 **False**, 자식 활동이 모두 완료 했을 때 작업을 완료 합니다. 기본값은 **null**합니다.|

## <a name="see-also"></a>참고자료

- [시퀀스](../workflow-designer/sequence-activity-designer.md)
- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [제어 흐름](../workflow-designer/control-flow-activity-designers.md)