---
title: "예외 문제 해결: System.Workflow.Activities.EventDeliveryFailedException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHWAEventDeliveryFailed"
helpviewer_keywords: 
  - "System.Workflow.Activities.EventDeliveryFailedException 예외"
  - "EventDeliveryFailedException 예외"
ms.assetid: 85ee2cb8-5cd1-4878-9421-2a78614e819f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Workflow.Activities.EventDeliveryFailedException
호스트에서 발생한 이벤트를 워크플로 인스턴스로 전달할 수 없는 경우 <xref:System.Workflow.Activities.EventDeliveryFailedException> 예외가 throw됩니다. 일반적으로 이 이벤트는 워크플로 인스턴스의 <xref:System.Workflow.Activities.ExternalDataExchangeService>에서 발생합니다. 이 클래스는 상속될 수 없습니다.  
  
## 설명  
 이 예외가 throw되는 경우 이벤트 로그에 `Event '{1}' on interface type '{0}' for instance id '{2}' cannot be delivered` 문자열이 추가됩니다.  
  
 상태 시스템 워크플로를 사용하는 경우 `Queue '{0}' is not enabled` 메시지와 함께 예외가 발생할 수 있습니다. 상태 시스템의 현재 상태에서 특정 이벤트를 처리할 수 없는 경우 이 예외가 발생합니다. 예를 들어 현재 상태를 제외한 다른 상태에 <xref:System.Workflow.Activities.EventDrivenActivity> 큐로 표시되는 <xref:System.Workflow.Activities.HandleExternalEventActivity>를 포함하는 `'{0}'`가 있는 경우 이 메시지가 발생합니다.  
  
## 참고 항목  
 <xref:System.Workflow.Activities.EventDeliveryFailedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)