---
title: "InitializeCorrelation 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.ServiceModel.Activities.InitializeCorrelation.UI"
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
caps.latest.revision: 6
caps.handback.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# InitializeCorrelation 활동 디자이너
**InitializeCorrelation** 활동 디자이너는 메시지를 보내거나 받기 전에 메시지 간 상관 관계를 설정하는 데 사용되는 <xref:System.ServiceModel.Activities.InitializeCorrelation> 활동을 만들고 구성하는 데 사용됩니다.  
  
## InitializeCorrelation 활동  
 <xref:System.ServiceModel.Activities.InitializeCorrelation> 활동은 메시지를 보내거나 받지 않고 상관 관계를 초기화하는 데 사용됩니다.일반적으로 상관 관계는 메시지를 보내거나 받을 때 초기화됩니다.메시지를 보내거나 받기 전에 상관 관계를 설정해야 하는 경우 <xref:System.ServiceModel.Activities.InitializeCorrelation>을 사용하여 상관 관계를 초기화합니다.  
  
### InitializeCorrelation 활동 디자이너 사용  
 **InitializeCorrelation** 활동 디자이너는 **도구 상자**의 **메시징** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **InitializeCorrelation** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 InitializeCorrelation이라는 이름의 <xref:System.ServiceModel.Activities.InitializeCorrelation> 활동이 만들어집니다.<xref:System.Activities.Activity.DisplayName%2A>은 **InitializeCorrelation** 활동 디자이너의 머리글 또는 **속성** 창의 **DisplayName** 상자에서 편집할 수 있습니다.  
  
 <xref:System.ServiceModel.Activities.CorrelationHandle>은 **InitializeCorrelation** 활동 디자이너 화면의 **속성** 창에 있는 **상관 관계** 필드에서 지정할 수 있습니다.  
  
 **속성** 창의 **CorrelationData** 필드 옆에 있는 줄임표 단추 또는 **InitializeCorrelation** 활동 디자이너 화면의 "보기..." 힌트 텍스트를 클릭하면 **상관 관계 초기화** 대화 상자가 표시됩니다. 이 대화 상자에서 상관 관계를 초기화하는 데 사용되는 키\-값 쌍과 상관 관계 핸들을 지정할 수 있습니다.이 대화 상자 사용 [!INCLUDE[crabout](../test/includes/crabout_md.md)][형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목을 참조하십시오.  
  
### InitializeCorrelation 속성  
 다음 표에서는 <xref:System.ServiceModel.Activities.InitializeCorrelation> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 **속성** 창이나 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 활동의 이름입니다.기본값은 InitializeCorrelation입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>에 꼭 기본값 이외의 값을 사용할 필요는 없지만 그런 값을 사용하는 것이 좋습니다.|  
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|상관 관계에서 워크플로 활동을 연결하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>입니다.|  
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|메시지를 워크플로 인스턴스와 연결하는 상관 관계 데이터의 사전입니다.<br /><br /> **상관 관계 초기화** 대화 상자를 사용하여 <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>를 구성합니다.이 대화 상자 사용 [!INCLUDE[crabout](../test/includes/crabout_md.md)][형식 컬렉션 편집기 대화 상자](../workflow-designer/type-collection-editor-dialog-box.md) 항목을 참조하십시오.|  
  
## 참고 항목  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [Receive](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Send](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)