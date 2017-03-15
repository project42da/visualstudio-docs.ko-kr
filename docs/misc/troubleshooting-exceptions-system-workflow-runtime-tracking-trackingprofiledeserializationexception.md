---
title: "예외 문제 해결: System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException | Microsoft Docs"
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
  - "EHWRTTrackingProfileDeserialization"
helpviewer_keywords: 
  - "System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException 예외"
  - "TrackingProfileDeserializationException 예외"
ms.assetid: ce8fe4c1-43e3-4930-947e-74b8d94f32bf
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException
<xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException>가 XML 문서를 <xref:System.Workflow.Runtime.Tracking.TrackingProfile>로 deserialize할 수 없는 경우에 <xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer> 예외가 throw됩니다.  
  
## 설명  
 <xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer>에서 이 예외를 throw할 때는 예외 원인을 설명하는 메시지도 제공합니다.<xref:System.Workflow.Runtime.Tracking.TrackingProfileSerializer>가 <xref:System.Workflow.Runtime.Tracking.TrackingProfile>을 deserialize하려는 동안 발생한 유효성 검사 오류 및 경고 목록을 제공하는 경우도 있습니다. 이와 같은 목록이 제공되는 경우 목록은 <xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException.ValidationEventArgs%2A> 속성에 포함되어 있습니다.  
  
## 참고 항목  
 <xref:System.Workflow.Runtime.Tracking.TrackingProfileDeserializationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)