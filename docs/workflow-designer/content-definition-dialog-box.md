---
title: "콘텐츠 정의 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "MessageContent.UI"
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
caps.handback.revision: 3
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 콘텐츠 정의 대화 상자
**콘텐츠 정의** 대화 상자는 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동의 **Content** 속성을 구성하는 데 사용됩니다.이 상자를 사용하는 활동 디자이너 [!INCLUDE[crabout](../test/includes/crabout_md.md)][Send](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md) 및 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목을 참조하십시오.  
  
 다음 표에서는 **상관 관계 초기화** 대화 상자의 UI\(사용자 인터페이스\) 요소에 대해 설명합니다.  
  
|UI 요소|설명|  
|-----------|--------|  
|**메시지**|**메시지 데이터** 식 입력란에서 메시지 콘텐츠를 지정하고 **메시지 형식** 드롭다운 목록 상자를 사용하여 메시지 형식을 지정합니다.**콘텐츠 정의**는 기본적으로 <xref:System.ServiceModel.Activities.ReceiveMessageContent>를 사용하며, 이를 위해서는 워크플로 서비스 정의에 <xref:System.ServiceModel.Channels.Message> 또는 메시지 계약 형식이 있어야 합니다.|  
|**매개 변수**|데이터 계약이 필요한 <xref:System.ServiceModel.Activities.ReceiveParametersContent>를 사용하려면 **매개 변수** 라디오 단추를 클릭하십시오.데이터 표를 사용하여 현재 워크플로의 가변 매개 변수에 값을 지정할 <xref:System.Activities.OutArgument> 키\/값 쌍의 제네릭 컬렉션을 설정합니다.|  
  
 **콘텐츠 정의** 대화 상자는 **Send**, **Receive**, **ReceiveAndSendReply** 및 **SendAndReceiveReply** 디자이너에 의해 사용됩니다.비슷한 방법으로 각각의 디자이너에 액세스할 수 있으며 여기서는 Receive 디자이너로 액세스 절차를 설명하겠습니다.  
  
 **Receive** 활동 디자이너를 **도구 상자**에서 끌어다가 일반적으로 활동을 배치하는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 Receive라는 이름의 <xref:System.ServiceModel.Activities.Receive> 활동이 만들어집니다.**Receive** 활동 디자이너를 선택하고 속성 표에 있는 **콘텐츠** 속성의 \(콘텐츠\) 텍스트 옆 줄임표 단추를 클릭하면 **콘텐츠 정의** 대화 상자가 나타납니다.  
  
 **메시지** 섹션에서는 <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동의 콘텐츠를, **매개 변수** 섹션에서는 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동의 콘텐츠를 지정할 수 있습니다.  
  
## 참고 항목  
 [Workflow Designer UI 도움말](../workflow-designer/workflow-designer-ui-help.md)