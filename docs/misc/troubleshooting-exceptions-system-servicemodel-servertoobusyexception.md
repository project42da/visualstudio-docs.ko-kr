---
title: "예외 문제 해결: System.ServiceModel.ServerTooBusyException | Microsoft Docs"
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
  - "System.ServiceModel.ServerTooBusyException 예외"
  - "ServerTooBusyException 예외"
ms.assetid: 80eb606a-ab3c-48af-b747-c9902989a059
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ServiceModel.ServerTooBusyException
서버 사용량이 많아 메시지를 받아들일 수 없는 경우 <xref:System.ServiceModel.ServerTooBusyException> 예외가 throw됩니다.  
  
## 설명  
 이 예외는 끝점 간 통신 중에 throw될 수 있는 복구 가능한 오류의 클래스를 나타내는 <xref:System.ServiceModel.CommunicationException>에서 파생됩니다. 강력한 클라이언트와 서비스 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 응용 프로그램에서 이러한 예외를 처리할 수 있습니다.<xref:System.ServiceModel.CommunicationException> 처리기가 보다 구체적인 <xref:System.ServiceModel.ServerTooBusyException>을 catch하지 못하게 하기 위해서 <xref:System.ServiceModel.CommunicationException>을 처리하기 전에 이 예외를 catch합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.ServerTooBusyException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)