---
title: "예외 문제 해결: System.ServiceModel.ServiceActivationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceActivationException 예외"
  - "System.ServiceModel.ServiceActivationException 예외"
ms.assetid: 32a3ea87-d6da-40bf-ba04-e862ac122391
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ServiceModel.ServiceActivationException
서비스를 활성화하지 못한 경우 <xref:System.ServiceModel.ServiceActivationException> 예외가 throw됩니다.  
  
## 설명  
 이 예외는 끝점 간 통신 중에 throw될 수 있으며 <xref:System.ServiceModel.CommunicationException>의 강력한 클라이언트와 서비스 응용 프로그램에서 처리할 수 있는 복구 가능한 오류의 클래스를 나타내는 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)]에서 파생됩니다. 보다 일반적인 <xref:System.ServiceModel.CommunicationException> 처리기가 보다 구체적인 <xref:System.ServiceModel.ActionNotSupportedException>을 catch하지 못하게 하기 위해서 <xref:System.ServiceModel.CommunicationException>을 처리하기 전에 이 예외를 catch합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceActivationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)