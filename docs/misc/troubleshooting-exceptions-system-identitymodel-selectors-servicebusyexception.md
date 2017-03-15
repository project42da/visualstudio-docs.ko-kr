---
title: "예외 문제 해결: System.IdentityModel.Selectors.ServiceBusyException | Microsoft Docs"
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
  - "ServiceBusyException 예외"
  - "System.IdentityModel.Selectors.ServiceBusyException 예외"
ms.assetid: 88acdc6b-45ad-40c6-aa5c-3b56244edcee
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IdentityModel.Selectors.ServiceBusyException
다른 요청을 처리하고 있기 때문에 CardSpace 서비스를 사용할 수 없는 경우 이를 나타내기 위해 <xref:System.IdentityModel.Selectors.ServiceBusyException> 예외가 throw됩니다. CardSpace는 요청을 큐에 대기시키지 않으며 한 번에 요청 하나만 처리할 수 있습니다.  
  
 다른 CardSpace 인스턴스가 실행 중인지 확인하여 실행되고 있으면 작업 관리자에서 icardagt.exe 프로세스를 중지하여 해당 인스턴스를 종료합니다.  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.ServiceBusyException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)