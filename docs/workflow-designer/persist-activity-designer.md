---
title: 워크플로 디자이너-Persist 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04c7989f5cc37ec295f9fa778f2120dd372fd99a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="persist-activity-designer"></a>Persist 활동 디자이너

**Persist** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Persist> 활동입니다.

## <a name="the-persist-activity"></a>Persist 활동

<xref:System.Activities.Statements.Persist> 활동은 워크플로를 디스크에 저장합니다(가능한 경우). <xref:System.Activities.Statements.Persist> 활동과 같은 비지속성 영역에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 실행할 수 없습니다. 비지속성 범위 내에서 <xref:System.Activities.Statements.Persist> 활동을 사용할 경우 런타임에 예외가 throw됩니다.

### <a name="using-the-persist-activity-designer"></a>Persist 활동 디자이너 사용

**Persist** 활동 디자이너에서 확인할 수 있습니다는 **런타임** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자** 탭 (또는 선택 **도구 상자** 에서 **보기** 메뉴나 CTRL + ALT + X.)

**Persist** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 <xref:System.Activities.Statements.Persist> 기본값 활동 **DisplayName** 영구적입니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **지속** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-persist-properties"></a>Persist 속성

다음 표에서는 <xref:System.Activities.Statements.Persist> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있습니다 및 그 중 일부는 워크플로 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Persist> 활동의 이름입니다. 기본값은 Persist입니다. 표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|

## <a name="see-also"></a>참고자료

- [런타임](../workflow-designer/runtime-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)