---
title: "예외 문제 해결: System.OperationCanceledException | Microsoft Docs"
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
  - "OperationCanceledException 클래스"
ms.assetid: 275e2887-7491-432b-9b80-a21bb794be29
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.OperationCanceledException
<xref:System.OperationCanceledException>은 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>이 `ThrowException`으로 설정된 상태에서 작업을 수행한 다음 취소한 경우에 throw됩니다.  
  
## 관련 팁  
 이 예외가 throw되지 않도록 하려면 <xref:System.OperationCanceledException>을 `DoNothing`으로 설정합니다.  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>의 기본값은 `ThrowException`입니다. 사용자가 작업을 취소해도 이 예외가 throw되지 않도록 하려면 열거형 값을 `DoNothing`으로 설정합니다.  
  
## 참고 항목  
 <xref:System.OperationCanceledException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)