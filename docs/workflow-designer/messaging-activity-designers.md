---
title: "메시징 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 897e63cf-a42f-4edd-876f-c4ccfffaf6d6
caps.latest.revision: 7
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 메시징 활동 디자이너
메시징 활동 디자이너는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램에서 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 메시지를 보내고 받는 메시징 활동을 만들고 구성하는 데 사용됩니다.[!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)]에는 다섯 가지 메시징 활동이 도입되었으며, [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에는 두 가지 새로운 템플릿 디자이너가 있어 워크플로 내의 메시징을 관리할 수 있습니다.이 단원의 항목 및 아래 표의 항목에서는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 활동 및 템플릿 디자이너의 사용 방법에 대한 지침을 제공합니다.  
  
## 단원 내용  
  
|메시지 활동|설명|  
|------------|--------|  
|[CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)|<xref:System.ServiceModel.Activities.CorrelationHandle> 개체로 자식 메시징 활동을 암시적으로 관리하는 <xref:System.ServiceModel.Activities.CorrelationScope> 활동을 만들고 구성합니다.|  
|[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)|메시지를 보내거나 받지 않고 상관 관계를 초기화하는 데 사용되는 <xref:System.ServiceModel.Activities.InitializeCorrelation> 활동을 만들고 구성합니다.|  
|[Receive](../workflow-designer/receive-activity-designer.md)|서비스로부터 메시지를 받는 <xref:System.ServiceModel.Activities.Receive> 활동을 만들고 구성합니다.|  
|[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)|<xref:System.Activities.Statements.Sequence> 활동 내부에 사전 구성된 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 쌍을 만듭니다.|  
|[Send](../workflow-designer/send-activity-designer.md)|서비스로 메시지를 보내는 <xref:System.ServiceModel.Activities.Send> 활동을 만들고 구성합니다.|  
|[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)|<xref:System.Activities.Statements.Sequence> 활동 내부에 사전 구성된 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동 쌍을 만듭니다.|  
|[TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)|워크플로에 대한 트랜잭션의 흐름을 가능하게 하는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 만들고 구성합니다.|  
  
## 참조  
 <xref:System.Activities.Activity>  
  
 <xref:System.ServiceModel.Activities.CorrelationScope>  
  
 <xref:System.ServiceModel.Activities.Receive>  
  
 <xref:System.ServiceModel.Activities.Send>  
  
 <xref:System.ServiceModel.Activities.ReceiveReply>  
  
 <xref:System.ServiceModel.Activities.SendReply>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
## 관련 단원  
 그 밖의 활동 디자이너 형식에 대해서는 다음 항목을 참조하십시오.  
  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)  
  
 [활동 디자이너 사용](../workflow-designer/using-the-activity-designers.md)  
  
 [순서도](../workflow-designer/flowchart-activity-designers.md)  
  
 [런타임](../workflow-designer/runtime-activity-designers.md)  
  
 [기본 형식](../workflow-designer/primitives-activity-designers.md)  
  
 [트랜잭션](../workflow-designer/transaction-activity-designers.md)  
  
 [컬렉션](../workflow-designer/collection-activity-designers.md)  
  
 [오류 처리](../workflow-designer/error-handling-activity-designers.md)  
  
## 외부 리소스  
 [활동 디자이너 사용](../workflow-designer/using-the-activity-designers.md)