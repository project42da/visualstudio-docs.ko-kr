---
title: 워크플로 디자이너-InitializeCorrelation 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24d319af36b5d07661213edb3cff48d376bd3736
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="initializecorrelation-activity-designer"></a>InitializeCorrelation 활동 디자이너

**InitializeCorrelation** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.ServiceModel.Activities.InitializeCorrelation> 보내거나 받기 전에 메시지 간의 상관 관계를 설정 하는 데 사용 되는 활동입니다.

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation 활동

<xref:System.ServiceModel.Activities.InitializeCorrelation> 활동은 메시지를 보내거나 받지 않고 상관 관계를 초기화하는 데 사용됩니다. 일반적으로 상관 관계는 메시지를 보내거나 받을 때 초기화됩니다. 메시지를 보내거나 받기 전에 상관 관계를 설정해야 하는 경우 <xref:System.ServiceModel.Activities.InitializeCorrelation>을 사용하여 상관 관계를 초기화합니다.

### <a name="using-the-initializecorrelation-activity-designer"></a>InitializeCorrelation 활동 디자이너 사용
 **InitializeCorrelation** 활동 디자이너에서 확인할 수 있습니다는 **메시징** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**  워크플로 디자이너에서 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **InitializeCorrelation** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 워크플로 디자이너 화면에 끌어 놓 및 합니다. 그렇기 때문에 <xref:System.ServiceModel.Activities.InitializeCorrelation> 기본값 활동 <xref:System.Activities.Activity.DisplayName%2A> InitializeCorrelation.The의 <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **InitializeCorrelation** 활동 디자이너 또는  **DisplayName** 상자는 **속성** 창.

 <xref:System.ServiceModel.Activities.CorrelationHandle> 수를 지정는 **상관 관계** 필드에 **속성** 창에는 **InitializeCorrelation** 활동 디자이너 화면 합니다.

 외에도 줄임표 단추를 클릭 하 여 **CorrelationData** 필드에 **속성** 창 또는 "보기..." 힌트 텍스트를 **InitializeCorrelation** 활동 디자이너 화면 표시는 **상관 관계 초기화** 초기화 하는 데 사용 되는 키-값 쌍과 상관 관계 핸들을 지정할 수 있는 대화 상자. 이 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목입니다.

### <a name="the-initializecorrelation-properties"></a>InitializeCorrelation 속성
 다음 표에서는 <xref:System.ServiceModel.Activities.InitializeCorrelation> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성을 편집할 수 있습니다 **속성** 창 또는 워크플로 디자이너 화면입니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 활동의 이름입니다. 기본값은 InitializeCorrelation입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>에 꼭 기본값 이외의 값을 사용할 필요는 없지만 그런 값을 사용하는 것이 좋습니다.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|상관 관계에서 워크플로 활동을 연결하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>입니다.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|메시지를 워크플로 인스턴스와 연결하는 상관 관계 데이터의 사전입니다.<br /><br /> 사용 하 여는 **상관 관계 초기화** 대화 상자를 구성할 수는 <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>합니다. 사용에 대 한 자세한 내용은이 대화 상자 참조는 [형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목입니다.|

## <a name="see-also"></a>참고자료

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [수신](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [보내기](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)