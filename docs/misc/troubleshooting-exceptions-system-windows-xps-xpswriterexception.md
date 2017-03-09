---
title: "예외 문제 해결: System.Windows.Xps.XpsWriterException | Microsoft Docs"
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
  - "EHWXXpsWriter"
helpviewer_keywords: 
  - "System.Windows.Xps.XpsWriterException 예외"
  - "XpsWriterException 예외"
ms.assetid: 3b9fbb94-ed67-44f2-82bb-af5cb5ada1ef
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Windows.Xps.XpsWriterException
<xref:System.Windows.Xps.XpsWriterException> 또는 <xref:System.Windows.Xps.XpsDocumentWriter> 개체의 현재 상태와 호환되지 않는 메서드가 호출되는 경우 <xref:System.Windows.Xps.VisualsToXpsDocument> 예외가 throw됩니다.  
  
## 설명  
 예를 들어 위와 같은 형식의 개체가 비동기 쓰기 작업을 수행하고 있지 않는데 `CancelAsync` 메서드가 호출되는 경우 이 예외가 throw됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Xps.XpsWriterException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)