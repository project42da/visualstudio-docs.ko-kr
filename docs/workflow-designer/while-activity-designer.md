---
title: 활동 디자이너는 동안 워크플로 디자이너-
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02f0e83f674378ca7f9297aedbeb580b4f2cad89
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="while-activity-designer"></a>While 활동 디자이너

<xref:System.Activities.Statements.While> 활동에 포함 된 활동을 실행 합니다. 해당 <xref:System.Activities.Statements.While.Body%2A> 동안 지정 된 <xref:System.Activities.Statements.While.Condition%2A> 계산 **true**합니다. 포함된 활동이 실행되지 않을 수도 있습니다. 포함된 활동이 적어도 한 번은 실행되도록 하려면 그 대신 <xref:System.Activities.Statements.DoWhile> 활동을 사용하세요.

## <a name="while-properties-in-workflow-designer"></a>Workflow Designer의 While 속성

다음 표에서는 가장 유용한 <xref:System.Activities.Statements.While> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.While> 활동 디자이너의 이름을 지정합니다. 기본값은 While입니다. 값을 편집할 수는 **속성** 창 또는 활동 디자이너 머리글에서 직접 합니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.While.Body%2A>|False|실행할 활동을 포함 하는 동안는 <xref:System.Activities.Statements.While.Condition%2A> 계산 **true**합니다.|
|<xref:System.Activities.Statements.While.Condition%2A>|True|확인 하기 위해 평가 하는 Visual Basic 식을 포함 하는지 여부를 활동에는 <xref:System.Activities.Statements.While.Body%2A> 를 실행 해야 합니다.|

## <a name="see-also"></a>참고자료

- [제어 흐름](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)