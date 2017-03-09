---
title: "예외 문제 해결: System.Printing.PrintingCanceledException | Microsoft Docs"
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
  - "PrintingCanceledException 예외"
  - "System.Printing.PrintingCanceledException 예외"
ms.assetid: bec418d6-f168-4a73-962f-5ee0427600b6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Printing.PrintingCanceledException
코드에서 취소된 인쇄 작업에 액세스하려고 하면 <xref:System.Printing.PrintingCanceledException> 예외가 발생합니다.  
  
## 설명  
 인쇄 기능을 포함하며 인쇄 작업 취소가 가능한 WPF\(Windows Presentation Foundation\) 응용 프로그램을 만드는 경우 이 예외를 올바르게 처리해야 합니다. 이러한 유형의 예외를 처리하지 않으면 Windows Presentation Foundation 응용 프로그램의 응답이 중지될 수 있습니다.  
  
## 참고 항목  
 <xref:System.Printing.PrintingCanceledException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)