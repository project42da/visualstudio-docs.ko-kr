---
title: "CorrelationScope 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.ServiceModel.Activities.CorrelationScope.UI"
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
caps.latest.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# CorrelationScope 활동 디자이너
**CorrelationScope** 활동 디자이너는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체를 사용하여 자식 메시징 활동을 암시적으로 관리하는 <xref:System.ServiceModel.Activities.CorrelationScope> 활동을 만들고 구성하는 데 사용됩니다.  
  
## CorrelationScope 활동  
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 속성은 자식 메시징 활동을 관리하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다.<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>에 포함된 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Receive> 활동은 해당 활동을 포함하는 <xref:System.ServiceModel.Activities.CorrelationScope> 활동의 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 속성을 사용하여 상호 연결을 수행하도록 구성됩니다.  
  
### CorrelationScope 활동 디자이너 사용  
 **CorrelationScope** 활동 디자이너는 **도구 상자**의 **메시징** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **CorrelationScope** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에 놓을 수 있습니다.그러면 기본 **DisplayName**인 CorrelationScope라는 이름의 <xref:System.ServiceModel.Activities.CorrelationScope> 활동이 만들어집니다.<xref:System.Activities.Activity.DisplayName%2A>은 **CorrelationScope** 활동 디자이너의 머리글 또는 **속성** 창의 **DisplayName** 상자에서 편집할 수 있습니다.  
  
 자식 메시징 활동에 사용할 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정하려면 **속성** 창의 **CorrelatesWith** 필드 옆에 있는 줄임표 단추를 클릭하여 **식 편집기** 대화 상자를 표시합니다.이 속성은 활동 디자이너 화면에서도 설정할 수 있습니다.  
  
 범위가 상관 관계 내부로 지정된 활동은 **CorrelationScope** 디자이너의 **본문** 상자 안에 해당 디자이너를 놓아 지정합니다.  
  
### CorrelationScope 속성  
 다음 표에서는 <xref:System.ServiceModel.Activities.CorrelationScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이 속성은 **속성** 창 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면에서 편집할 수 있으며, 흔히 양쪽 모두에서 편집 가능합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 활동의 선택적 이름입니다.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|자식 메시징 활동을 관리하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다.이 속성을 설정하지 않으면 <xref:System.ServiceModel.Activities.CorrelationScope>는 자동으로 <xref:System.ServiceModel.Activities.CorrelationHandle>을 만듭니다.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|상관 관계 범위 내에 활동을 지정합니다.|  
  
## 참고 항목  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Receive](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Send](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)