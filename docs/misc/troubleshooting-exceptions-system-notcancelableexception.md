---
title: "예외 문제 해결: System.NotCancelableException | Microsoft Docs"
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
  - "NotCancelableException 클래스"
ms.assetid: 36b82d4b-f075-4af5-993a-3e763a7e254a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.NotCancelableException
`NotCancelableException`은 취소할 수 없는 작업을 취소하려는 경우에 throw됩니다.  
  
## 관련 팁  
 작업을 취소하지 마십시오.  
 일부 작업은 취소할 수 없으며 이러한 작업을 취소하면 이 예외가 throw됩니다. 이와 같은 경우에는 작업 취소 옵션을 사용자에게 제공하지 않도록 합니다.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)