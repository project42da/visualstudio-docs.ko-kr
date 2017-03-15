---
title: "다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다.
지정한 소스가 다른 이벤트 로그와 함께 등록되어 있는 이벤트 로그에 항목을 쓰려고 했습니다.  
  
 구성 요소가 로그에 항목을 쓰기 전에 <xref:System.Diagnostics.EventLog> 구성 요소 인스턴스의 <xref:System.Diagnostics.EventLog.Source%2A> 속성을 설정해야 합니다. 이때 시스템에서 구성 요소가 쓰고 있는 이벤트 로그에 지정한 소스가 등록되어 있는지 확인하고 필요한 경우 <xref:System.Diagnostics.EventLog.CreateEventSource%2A>를 호출합니다.  
  
### 이 오류를 해결하려면  
  
1.  소스와 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 또는 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 메서드를 사용하는 첫 번째 로그의 연결을 제거합니다.  
  
2.  새 로그에 소스를 등록합니다.  
  
## 참고 항목  
 [My.Application.Log 개체](/dotnet/visual-basic/language-reference/objects/my-application-log-object)   
 [How to: Remove an Event Source](http://msdn.microsoft.com/ko-kr/bc66c900-4b8a-426a-b8e2-17031a20167e)   
 [How to: Add Your Application as a Source of Event Log Entries](http://msdn.microsoft.com/ko-kr/948ff920-a739-4e66-a191-ee951512d42c)