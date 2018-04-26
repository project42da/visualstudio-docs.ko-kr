---
title: 워크플로 디자이너-Compensate 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8278066a12df0d195770391d0b2f3144ba16487d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="compensate-activity-designer"></a>Compensate 활동 디자이너

**Compensate** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Compensate> 활동입니다.

## <a name="the-compensate-activity"></a>Compensate 활동
 <xref:System.Activities.Statements.Compensate> 활동은 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>에 포함된 활동에 대해 <xref:System.Activities.Statements.CompensableActivity>를 명시적으로 호출합니다. <xref:System.Activities.Statements.Compensate>, <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> 또는 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>의 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>에서 <xref:System.Activities.Statements.CompensableActivity> 활동을 사용하지 않는 경우 <xref:System.Activities.Statements.Compensate.Target%2A> 속성을 지정해야 합니다.

 <xref:System.Activities.Statements.CompensationToken>에 의해 지정된 <xref:System.Activities.Statements.Compensate.Target%2A>은 <xref:System.Activities.Statements.CompensableActivity>의 <xref:System.Activities.Statements.CompensableActivity.Body%2A>가 성공적으로 완료된 후 <xref:System.Activities.Statements.CompensableActivity>를 명시적으로 확인하거나 보정하는 수단을 제공합니다.

### <a name="using-the-compensate-activity-designer"></a>Compensate 활동 디자이너 사용
 **Compensate** 활동 디자이너에서 확인할 수 있습니다는 **트랜잭션** 의 범주는 **도구 상자**합니다. 열려는 **도구 상자**을 선택는 **도구 상자** 워크플로 디자이너의 왼쪽에 탭 (또는 선택 **도구 모음** 에서 **보기**메뉴나 CTRL + ALT + X.)

 **Compensate** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 활동 디자이너 만들어집니다는 <xref:System.Activities.Statements.Compensate> 기본값 활동 <xref:System.Activities.Activity.DisplayName%2A> Compensate입니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **Compensate** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-compensate-properties"></a>보정 속성
 다음 표에서는 <xref:System.Activities.Statements.CancellationScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. <xref:System.Activities.Activity.DisplayName%2A> 또는 워크플로 디자이너 화면 속성 그리드에서 속성을 편집할 수 있습니다. 편집 된 <xref:System.Activities.Statements.Compensate.Target%2A> 속성 표에 속성입니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Compensate> 활동의 선택적 이름을 지정합니다. 기본값은 Compensate입니다.|
|<xref:System.Activities.Statements.Compensate.Target%2A>|True|이 <xref:System.Activities.InArgument%601> 활동의 <xref:System.Activities.Statements.CompensationToken>이 들어 있는 <xref:System.Activities.Statements.Compensate>을 지정합니다.|

## <a name="see-also"></a>참고자료

- [트랜잭션](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate 활동 디자이너](../workflow-designer/compensate-activity-designer.md)
- [확인](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)