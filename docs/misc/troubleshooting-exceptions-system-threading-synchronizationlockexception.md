---
title: "예외 문제 해결: System.Threading.SynchronizationLockException | Microsoft Docs"
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
  - "SynchronizationLockException 예외"
  - "System.Threading.SynchronizationLockException 예외"
ms.assetid: 82d80643-fc5c-40ae-a579-46869772d25c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Threading.SynchronizationLockException
지정된 `Monitor`에 대한 잠금을 메서드의 호출자가 소유하고 있어야 하지만 메서드를 호출한 호출자가 이 잠금을 소유하지 않은 경우 throw되는 예외입니다.  
  
## 설명  
 <xref:System.Threading.SynchronizationLockException>은 동기화되지 않은 코드 블록에서 <xref:System.Threading.Monitor.Exit%2A> 클래스의 <xref:System.Threading.Monitor.Pulse%2A>, <xref:System.Threading.Monitor.PulseAll%2A>, <xref:System.Threading.Monitor.Wait%2A> 및 `Monitor` 메서드를 호출하는 경우에 throw됩니다.  
  
## 참고 항목  
 <xref:System.Threading.SynchronizationLockException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)