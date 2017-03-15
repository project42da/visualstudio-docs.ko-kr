---
title: "예외 문제 해결: System.Data.StrongTypingException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "StrongTypingException 클래스"
ms.assetid: 90859ce2-3696-43cb-baf4-7daf98d8e2e1
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.StrongTypingException
<xref:System.Data.StrongTypingException>은 사용자가 강력한 형식의 <xref:System.DBNull>의 <xref:System.Data.DataTable.DataSet%2A> 값에 액세스할 때 발생합니다.  
  
## 관련 팁  
 **StrongTypingException의 오류 처리를 추가하십시오.**  
 <xref:System.Data.DataTable.DataSet%2A>에 액세스하는 코드를 `Try…Catch` 블록에 배치하고 <xref:System.Data.StrongTypingException>을 catch합니다.  
  
## 참고 항목  
 <xref:System.Data.DataTable.DataSet%2A>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)