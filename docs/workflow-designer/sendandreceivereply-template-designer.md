---
title: SendAndReceiveReply 템플릿 디자이너-워크플로 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c6a4749ed138b22ac3d600befad01ef1776478e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply 템플릿 디자이너

**SendAndReceiveReply** 서식 파일의 쌍을 만드는 데 사용 되 미리 구성 된 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 내에서 활동을 <xref:System.Activities.Statements.Sequence> 요청/응답 메시지 교환의 일환으로 상관 관계에 있는 활동 클라이언트에서 패턴입니다.

## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply 템플릿

추가 **SendAndReceiveReply** 만드는 것 외에도 세 가지 작업을 수행 하는 서식 파일은 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 내의 활동은 <xref:System.Activities.Statements.Sequence> 활동:

1.  <xref:System.ServiceModel.Activities.Send.OperationName%2A> 활동의 <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Send> 속성이 구성됩니다.

2.  <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> 활동의 <xref:System.ServiceModel.Activities.ReceiveReply> 속성이 <xref:System.ServiceModel.Activities.Send> 활동에 바인딩됩니다.

3.  부모 활동의 변수로 <xref:System.ServiceModel.Activities.CorrelationHandle>이 만들어집니다.

### <a name="using-the-sendandreceivereply-template-designer"></a>SendAndReceiveReply 템플릿 디자이너 사용
 **SendAndReceiveReply** 활동 디자이너에서 확인할 수 있습니다는 **메시징** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**  워크플로 디자이너에서 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **SendAndReceiveReply** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 가 일반적으로 활동을 배치 하는 경우 워크플로 디자이너 화면에 끌어 놓 및 합니다. 그렇기 때문에 <xref:System.ServiceModel.Activities.Send> 활동으로 구성할 수는 **보낼** 활동 디자이너와는 상관 관계가 지정 된 <xref:System.ServiceModel.Activities.ReceiveReply> 로 구성할 수 있습니다는 **ReceiveReplyForSend** 디자이너입니다.

 사용에 대 한 자세한 내용은 **보낼** 구성 하는 디자이너는 <xref:System.ServiceModel.Activities.Send> 활동 참조는 [보낼](../workflow-designer/send-activity-designer.md) 항목입니다.

 사용 하는 방법에 대 한 자세한 내용은 **ReceiveReplyForSend** 구성 하는 디자이너는 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 다음 섹션을 참조 하세요.

### <a name="properties-of-receivereply"></a>ReceiveReply의 속성
 다음 표에서는 <xref:System.ServiceModel.Activities.ReceiveReply> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있습니다 및 일부 워크플로 Designerdesigner 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.ReceiveReply> 활동의 선택적 이름입니다. 기본값은 ReceiveReplyForSend입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>에 꼭 기본값 이외의 값을 사용할 필요는 없지만 그런 값을 사용하는 것이 좋습니다.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|True|이 <xref:System.ServiceModel.Activities.Send> 활동과 한 쌍을 이루는 <xref:System.ServiceModel.Activities.ReceiveReply> 활동에 대한 참조입니다. 이 속성 아니어야 **null**합니다. <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동은 클라이언트에서 요청/응답 메시징 패턴을 모델링하는 데 함께 사용됩니다. 이 속성은 쌍을 이루는 <xref:System.ServiceModel.Activities.Send> 활동을 지정합니다. 이 속성은 <xref:System.ServiceModel.Activities.Send> 활동을 만들었던 <xref:System.ServiceModel.Activities.ReceiveReply> 활동에 자동으로 바인딩되기 때문에 디자이너에서 편집할 수 없습니다.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|받을 메시지 또는 매개 변수 콘텐츠를 지정합니다. <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동이거나 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동일 수 있습니다. 옆에 있는 줄임표 단추를 클릭 하 여이 속성을 편집는 **콘텐츠** 필드에 속성 표 또는 클릭 하 고 **정의...**  옆에 있는 단추는 **콘텐츠** 에 레이블는 **수신** 활동 디자이너 화면입니다. 둘 다 표시는 **콘텐츠 정의** 대화 상자. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목입니다.|
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|워크플로 내에서 이 <xref:System.ServiceModel.Activities.CorrelationInitializer> 활동을 구성하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 여러 개 초기화하는 <xref:System.ServiceModel.Activities.Receive> 개체 컬렉션을 지정합니다. 옆에 있는 줄임표 단추를 클릭는 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 열려는 속성 표에서 속성에에서는 **상관 관계 이니셜라이저 추가** 대화 상자. 이 상자를 사용 하는 방법에 대 한 자세한 내용은 참조는 [CorrelationInitializers 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md) 항목입니다.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|메시지의 동작 헤더를 지정합니다. 동작 헤더가 명시적으로 설정되어 있지 않으면 기본값인<br /><br /> **https://tempuri.org/{service 계약 네임 스페이스} / {서비스 계약 이름} / {/{operation name}.**|

## <a name="see-also"></a>참고자료

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [수신](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [보내기](../workflow-designer/send-activity-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)