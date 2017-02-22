---
title: "SendAndReceiveReply 템플릿 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.ServiceModel.Activities.SendAndReceiveReply.UI"
  - "System.ServiceModel.Activities.ReceiveReply.UI"
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
caps.latest.revision: 6
caps.handback.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# SendAndReceiveReply 템플릿 디자이너
**SendAndReceiveReply** 템플릿은 클라이언트의 요청\/응답 메시지 교환 패턴 중 상호 연결되는 <xref:System.Activities.Statements.Sequence> 활동 내의 사전 구성된 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 쌍을 만드는 데 사용됩니다.  
  
## SendAndReceiveReply 템플릿  
 **SendAndReceiveReply** 템플릿을 추가하면 <xref:System.Activities.Statements.Sequence> 활동 내에 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동이 만들어지는 것 외에 다음 세 가지 일이 더 이루어집니다.  
  
1.  <xref:System.ServiceModel.Activities.Send> 활동의 <xref:System.ServiceModel.Activities.Send.OperationName%2A>, <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> 속성이 구성됩니다.  
  
2.  <xref:System.ServiceModel.Activities.ReceiveReply> 활동의 <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> 속성이 <xref:System.ServiceModel.Activities.Send> 활동에 바인딩됩니다.  
  
3.  부모 활동의 변수로 <xref:System.ServiceModel.Activities.CorrelationHandle>이 만들어집니다.  
  
### SendAndReceiveReply 템플릿 디자이너 사용  
 **SendAndReceiveReply** 활동 디자이너는 **도구 상자**의 **메시징** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **SendAndReceiveReply** 활동 디자이너를 **도구 상자**에서 끌어다가 일반적으로 활동을 배치하는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 놓을 수 있습니다.그러면 **Send** 활동 디자이너로 구성할 수 있는 <xref:System.ServiceModel.Activities.Send> 활동과 **ReceiveReplyForSend** 디자이너로 구성할 수 있는 상호 연관된 <xref:System.ServiceModel.Activities.ReceiveReply>가 만들어집니다.  
  
 **Send** 디자이너를 사용하여 <xref:System.ServiceModel.Activities.Send> 활동을 구성하는 방법[!INCLUDE[crabout](../test/includes/crabout_md.md)][Send](../workflow-designer/send-activity-designer.md) 항목을 참조하십시오.  
  
 **ReceiveReplyForSend** 디자이너를 사용하여 <xref:System.ServiceModel.Activities.ReceiveReply> 활동을 구성하는 방법[!INCLUDE[crabout](../test/includes/crabout_md.md)] 다음 단원을 참조하십시오.  
  
### ReceiveReply의 속성  
 다음 표에서는 <xref:System.ServiceModel.Activities.ReceiveReply> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.ReceiveReply> 활동의 선택적 이름입니다.기본값은 ReceiveReplyForSend입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>에 꼭 기본값 이외의 값을 사용할 필요는 없지만 그런 값을 사용하는 것이 좋습니다.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|True|이 <xref:System.ServiceModel.Activities.ReceiveReply> 활동과 한 쌍을 이루는 <xref:System.ServiceModel.Activities.Send> 활동에 대한 참조입니다.이 속성은 **null**이 아니어야 합니다.<xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동은 클라이언트에서 요청\/응답 메시징 패턴을 모델링하는 데 함께 사용됩니다.이 속성은 쌍을 이루는 <xref:System.ServiceModel.Activities.Send> 활동을 지정합니다.이 속성은 <xref:System.ServiceModel.Activities.ReceiveReply> 활동을 만들었던 <xref:System.ServiceModel.Activities.Send> 활동에 자동으로 바인딩되기 때문에 디자이너에서 편집할 수 없습니다.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|받을 메시지 또는 매개 변수 콘텐츠를 지정합니다.<xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동이거나 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동일 수 있습니다.속성 표의 **콘텐츠** 필드 옆에 있는 줄임표 단추를 클릭하거나 **Receive** 활동 디자이너 화면의 **콘텐츠** 레이블 옆에 있는 **정의…** 단추를 클릭하여 이 속성을 편집할 수 있습니다.둘 모두 **콘텐츠 정의** 대화 상자를 표시합니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][콘텐츠 정의 대화 상자](../workflow-designer/content-definition-dialog-box.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|워크플로 내에서 이 <xref:System.ServiceModel.Activities.Receive> 활동을 구성하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 여러 개 초기화하는 <xref:System.ServiceModel.Activities.CorrelationInitializer> 개체 컬렉션을 지정합니다.속성 표에서 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 속성 옆의 줄임표 단추를 클릭하여 **상관 관계 이니셜라이저 추가** 대화 상자를 엽니다.이 상자를 사용하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md) 항목을 참조하십시오.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|메시지의 동작 헤더를 지정합니다.동작 헤더가 명시적으로 설정되어 있지 않으면 기본값인<br /><br /> **https:\/\/tempuri.org\/{service contract namespace}\/{service contract name}\/{operation name}을 사용합니다.**|  
  
## 참고 항목  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Receive](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Send](../workflow-designer/send-activity-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)