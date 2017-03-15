---
title: "예외 문제 해결: System.IO.EndOfStreamException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "EndOfStreamException 클래스"
ms.assetid: 1271e6f6-3a0d-49f0-9ff4-178d480687be
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IO.EndOfStreamException
<xref:System.IO.EndOfStreamException> 예외는 스트림의 끝을 지나서 읽으려는 경우에 throw됩니다.  
  
## 관련 팁  
 **파일을 읽기 전에 파일의 끝에 도달했는지 확인하십시오.**  
 스트림에서 읽기 전에 파일의 끝을 확인하려면 <xref:System.IO.StreamReader.Peek%2A> 메서드를 사용합니다.  
  
## 참고 항목  
 <xref:System.IO.EndOfStreamException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../Topic/How%20to:%20Read%20and%20Write%20to%20a%20Newly%20Created%20Data%20File.md)   
 [방법: 로그 파일 열기 및 추가](../Topic/How%20to:%20Open%20and%20Append%20to%20a%20Log%20File.md)