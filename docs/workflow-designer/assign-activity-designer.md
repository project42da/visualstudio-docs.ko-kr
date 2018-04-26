---
title: 워크플로 디자이너-Assign 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44d825d5d6ee36876c807ce067c71c1b10896623
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="assign-activity-designer"></a>Assign 활동 디자이너

**할당** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Assign> 활동입니다.

## <a name="the-assign-activity"></a>Assign 활동

<xref:System.Activities.Statements.Assign> 활동은 변수 또는 인수에 값을 할당합니다.

### <a name="using-the-assign-activity-designer"></a>Assign 활동 디자이너 사용

**할당** 활동 디자이너에서 확인할 수 있습니다는 **기본 형식** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**탭 (또는 선택 **도구 상자** 에서 **보기** 메뉴나 CTRL + ALT + X.)

**할당** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은, 등 배치 변한 경우 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 삭제는 **할당** 활동 디자이너 만듭니다는 <xref:System.Activities.Statements.Assign> 기본값 활동 **DisplayName** 할당의 합니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **할당** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-assign-properties"></a>Assign 속성

다음 표에서는 <xref:System.Activities.Statements.Assign> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있습니다 및 그 중 일부는 워크플로 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Assign> 활동의 이름입니다. 기본값은 Assign입니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.Assign.To%2A>|True|<xref:System.Activities.Statements.Assign.Value%2A>가 할당되는 변수 또는 인수입니다. 값은 유효한 Visual Basic 식별자 여야 합니다. Visual Basic 식을 입력 속성을 설정 하는 **를** 상자에 **할당** 활동 디자이너나 속성 표의 합니다.|
|<xref:System.Activities.Statements.Assign.Value%2A>|True|변수에 할당된 값입니다. 설정 하는 <xref:System.Activities.Statements.Assign.Value%2A>, Visual Basic 식을 입력는 **값** 상자에 **할당** 활동 디자이너나 속성 표의 합니다.|

## <a name="see-also"></a>참고자료

- [Primitives](../workflow-designer/primitives-activity-designers.md)
- [지연](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)