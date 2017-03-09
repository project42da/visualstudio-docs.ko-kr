---
title: "예외 문제 해결: System.Workflow.Runtime.Hosting.PersistenceException | Microsoft Docs"
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
  - "EHWRHPersistence"
helpviewer_keywords: 
  - "PersistenceException 예외"
  - "System.Workflow.Runtime.Hosting.PersistenceException 예외"
ms.assetid: cb2fb820-f990-4728-9a7f-5ec6fd8d5b10
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Workflow.Runtime.Hosting.PersistenceException
유지 서비스에서 요청을 수행할 수 없는 경우 <xref:System.Workflow.Runtime.Hosting.PersistenceException> 예외가 throw됩니다.  
  
## 설명  
 완료된 범위나 워크플로 인스턴스 상태를 데이터베이스에 커밋하기 위한 요청을 완료할 수 없는 경우 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>에서 <xref:System.Workflow.Runtime.Hosting.PersistenceException>을 throw합니다.  
  
 유지 서비스를 <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> 클래스 또는 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> 클래스에서 파생시켜 구현한 경우 워크플로 런타임 엔진의 요청을 수행하지 못하게 하는 서비스의 오류 조건을 나타내는 적절한 메시지와 함께 <xref:System.Workflow.Runtime.Hosting.PersistenceException>을 throw할 수 있습니다.  
  
 자세한 내용은 <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService>를 참조하세요.  
  
## 참고 항목  
 <xref:System.Workflow.Runtime.Hosting.PersistenceException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)