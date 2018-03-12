---
title: "TransactedReceiveScope 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 76dfb7002c200f0dc920c4c3aae20b1d97faa6e2
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope 활동 디자이너
**TransactedReceiveScope** 디자이너 만들고 구성 하는 데 사용 됩니다는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동입니다.

## <a name="the-transactedreceivescope-activity"></a>TransactedReceiveScope 활동
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 통해 트랜잭션을 워크플로 또는 디스패처에 의해 만들어진 서버 트랜잭션으로 이동할 수 있습니다.

### <a name="using-the-transactedreceivescope-activity-designer"></a>TransactedReceiveScope 활동 디자이너 사용
 **TransactedReceiveScope** 활동 디자이너에서 확인할 수 있습니다는 **메시징** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**  탭 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **TransactedReceiveScope** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로 배치 합니다. 그렇기 때문에 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 기본값 활동 **DisplayName** TransactedReceiveScope입니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **TransactedReceiveScope** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

 **TransactedReceiveScope** 디자이너에 포함 되어 **요청** 및 **본문** 상자입니다. 이 상자는 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> 속성을 구성하는 데 사용되고, 이 속성은 <xref:System.ServiceModel.Activities.Receive> 활동과 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> 속성을 지정하며, 이 속성은 다시 몇 가지 다른 <xref:System.Activities.Activity>를 지정합니다. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>는 트랜잭션을 만듭니다. 그러면 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> 범위의 트랜잭션이 앰비언트 트랜잭션이 되어 이 범위의 모든 활동이 이 트랜잭션 내에서 실행됩니다.

### <a name="the-transactedreceivescope-properties"></a>TransactedReceiveScope 속성
 다음 표에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 <xref:System.Activities.Activity.DisplayName%2A> 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있지만 나머지 속성은 반드시 디자이너 화면에서 편집해야 합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동의 선택적 이름입니다. 기본값은 TransactedReceiveScope입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|True|삭제는 <xref:System.ServiceModel.Activities.Receive> 활동에는 **요청** 활동 디자이너 화면에서 블록입니다.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|삭제는 <xref:System.Activities.Activity> 에 **본문** 활동 디자이너 화면에서 블록입니다.|

## <a name="see-also"></a>참고 항목

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [수신](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [보내기](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)