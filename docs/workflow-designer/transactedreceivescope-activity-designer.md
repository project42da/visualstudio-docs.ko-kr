---
title: TransactedReceiveScope 활동 디자이너-워크플로 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c7f5c4cd48cc98d58da278ac53c1a829d15c43cd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope 활동 디자이너

**TransactedReceiveScope** 디자이너 만들고 구성 하는 데 사용 됩니다는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동입니다.

## <a name="the-transactedreceivescope-activity"></a>TransactedReceiveScope 활동

<xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 통해 트랜잭션을 워크플로 또는 디스패처에 의해 만들어진 서버 트랜잭션으로 이동할 수 있습니다.

### <a name="using-the-transactedreceivescope-activity-designer"></a>TransactedReceiveScope 활동 디자이너 사용
 **TransactedReceiveScope** 활동 디자이너에서 확인할 수 있습니다는 **메시징** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**  워크플로 디자이너에서 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **TransactedReceiveScope** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 가 일반적으로 활동을 배치 하는 경우 워크플로 디자이너 화면에 끌어 놓 및 합니다. 그렇기 때문에 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 기본값 활동 **DisplayName** TransactedReceiveScope입니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **TransactedReceiveScope** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

 **TransactedReceiveScope** 디자이너에 포함 되어 **요청** 및 **본문** 상자입니다. 이 상자는 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> 속성을 구성하는 데 사용되고, 이 속성은 <xref:System.ServiceModel.Activities.Receive> 활동과 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> 속성을 지정하며, 이 속성은 다시 몇 가지 다른 <xref:System.Activities.Activity>를 지정합니다. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>는 트랜잭션을 만듭니다. 그러면 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> 범위의 트랜잭션이 앰비언트 트랜잭션이 되어 이 범위의 모든 활동이 이 트랜잭션 내에서 실행됩니다.

### <a name="the-transactedreceivescope-properties"></a>TransactedReceiveScope 속성
 다음 표에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 <xref:System.Activities.Activity.DisplayName%2A> 속성 속성 표에서 또는 워크플로 디자이너 화면에서 편집할 수 있지만 다른 디자인 화면에서 편집 해야 합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동의 선택적 이름입니다. 기본값은 TransactedReceiveScope입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|True|삭제는 <xref:System.ServiceModel.Activities.Receive> 활동에는 **요청** 활동 디자이너 화면에서 블록입니다.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|삭제는 <xref:System.Activities.Activity> 에 **본문** 활동 디자이너 화면에서 블록입니다.|

## <a name="see-also"></a>참고자료

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [수신](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [보내기](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)