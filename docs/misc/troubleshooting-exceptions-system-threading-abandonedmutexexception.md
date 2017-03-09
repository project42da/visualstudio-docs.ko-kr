---
title: "예외 문제 해결: System.Threading.AbandonedMutexException | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.Threading.AbandonedMutexException 예외"
  - "AbandonedMutexException 예외"
ms.assetid: 11157066-32ed-492c-83af-29983f915eec
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Threading.AbandonedMutexException
스레드 하나가 뮤텍스 개체에서 대기 중인 동안 다른 스레드가 뮤텍스를 해제하지 않은 채 종료되여 이를 중단한 경우 throw되는 예외입니다.  
  
## 설명  
 중단된 뮤텍스는 일반적으로 코드의 심각한 오류를 나타냅니다. 스레드가 뮤텍스를 해제하지 않은 채 종료되면 뮤텍스의 보호를 받는 데이터 구조의 상태가 일관되지 않을 수 있습니다. 데이터 구조의 무결성을 확인할 수 있으면 뮤텍스에 대한 소유권을 요청하는 다음 스레드에서 이 예외를 처리하고 작업을 계속 진행할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Threading.AbandonedMutexException>   
 <xref:System.Threading.Mutex>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)