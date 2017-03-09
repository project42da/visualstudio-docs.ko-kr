---
title: "예외 문제 해결: System.Exception | Microsoft Docs"
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
  - "System.Exception 예외"
  - "기본 클래스, 예외"
  - "예외, 기본 클래스"
ms.assetid: fc15931a-9323-47c6-a42f-55d0534b939a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Exception
응용 프로그램을 실행할 때 나타나는 오류를 나타냅니다. 이 클래스는 모든 예외에 대한 기본 클래스입니다.  
  
## 관련 팁  
 **자세한 정보를 보려면 InnerException 속성을 확인하세요.**  
 오류를 해결하려면 현재 예외의 원인이 된 내부\(이전\) 예외에 대한 정보가 필요할 수 있습니다. 현재 예외의 <xref:System.Exception.InnerException%2A> 속성에는 내부 예외가 들어 있습니다.**예외 도우미** 대화 상자의 **자세히 보기** 링크를 사용하여 <xref:System.Exception.InnerException%2A> 속성에 액세스할 수 있습니다.  
  
 **임시로 내 코드만 디버깅 옵션을 해제합니다.**  
 사용자가 작성하지 않은 코드에서 예외가 발생할 수 있습니다. 이러한 코드를 디버깅하려면 내 코드만 디버깅 옵션을 해제해야 합니다. 자세한 내용은 [옵션 대화 상자, 디버깅, 일반](../debugger/general-debugging-options-dialog-box.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Exception>   
 <xref:System.Exception.InnerException%2A>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [방법: 예외가 throw되었을 때 중단](../misc/how-to-break-when-an-exception-is-thrown.md)   
 [옵션 대화 상자, 디버깅, 일반](../debugger/general-debugging-options-dialog-box.md)