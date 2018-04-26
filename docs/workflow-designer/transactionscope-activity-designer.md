---
title: TransactionScope 활동 디자이너-워크플로 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 67c8a5c610492f298d3f2ef6de35444c96f7310f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="transactionscope-activity-designer"></a>TransactionScope 활동 디자이너

**TransactionScope** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.TransactionScope> 활동입니다.

## <a name="the-transactionscope-activity"></a>TransactionScope 활동
 <xref:System.Activities.Statements.TransactionScope> 활동은 단일 트랜잭션에 포함된 활동을 실행합니다. 해당 트랜잭션의 <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동 및 다른 모든 참가자가 성공적으로 완료되면 트랜잭션이 커밋됩니다.

### <a name="using-the-transactionscope-activity-designer"></a>TransactionScope 활동 디자이너 사용
 **TransactionScope** 활동 디자이너에서 확인할 수 있습니다는 **트랜잭션** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**  워크플로 디자이너의 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **TransactionScope** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그러면 기본 <xref:System.Activities.Statements.TransactionScope>인 TransactionScope라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **TransactionScope** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-transactionscope-properties"></a>TransactionScope 속성
 다음 표에서는 <xref:System.Activities.Statements.TransactionScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. <xref:System.Activities.Activity.DisplayName%2A> 및 <xref:System.Activities.Statements.TransactionScope.Body%2A> 워크플로 디자이너 화면에서 속성을 편집할 수 있습니다. 그러나 다른 속성은 속성 표에서 편집해야 합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TransactionScope> 활동의 선택적 이름입니다. 기본값은 TransactionScope입니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|단일 트랜잭션에서 실행할 활동을 지정합니다. 추가 하는 <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동의 활동의 **도구 상자** 에 **본문** 상자에 **TransactionScope** 힌트 텍스트가 "작업 놓기 활동 디자이너 "여기에 있습니다.|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|이 <xref:System.Transactions.IsolationLevel>의 <xref:System.Activities.Statements.TransactionScope>을 지정합니다.|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|트랜잭션을 완료해야 하는 시간 간격(시:분:초를 의미하는 00:00:00 형식)을 지정합니다. 기본값은 1분입니다(00:01:00).|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|True|트랜잭션이 중단되면 워크플로를 중단할지 여부를 나타내는 값을 지정합니다.|

## <a name="see-also"></a>참고자료

- [트랜잭션](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [보정](../workflow-designer/compensate-activity-designer.md)
- [확인](../workflow-designer/confirm-activity-designer.md)