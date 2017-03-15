---
title: "EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.
`EventLog`에서 다른 로그에 등록된 소스를 참조하려고 합니다. 이벤트 로그에 항목을 쓰는 경우 <xref:System.Diagnostics.EventLog.Source%2A> 속성을 지정해야 합니다.<xref:System.Diagnostics.EventLog.Source%2A> 속성은 구성 요소를 항목의 유효한 소스로 이벤트 로그에 등록합니다. 단일 소스는 한 번에 하나의 이벤트 로그에만 연결되고 항목을 쓸 수 있습니다.  
  
 기본적으로 구성 요소를 유효한 소스로 먼저 등록하지 않고 항목을 쓰려고 하면 시스템이 자동으로 <xref:System.Diagnostics.EventLog.Source%2A> 속성의 값을 소스 문자열로 사용하여 이벤트 로그에 소스를 등록합니다.  
  
### 이 오류를 해결하려면  
  
-   소스가 올바른 로그에 등록되었는지 확인합니다. 이렇게 하려면 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 메서드 또는 해당 오버로드 중 하나를 사용하여 이벤트 로그에 구성 요소를 고유하게 식별하는 문자열을 지정합니다.  
  
## 참고 항목  
 [Administering Event Logs](http://msdn.microsoft.com/ko-kr/35f53238-bdd2-417b-acd8-2fd9f7397f18)   
 [Event Log References](http://msdn.microsoft.com/ko-kr/4af0661c-6c96-49f4-961d-b26ed9bc3e87)   
 [How to: Add Your Application as a Source of Event Log Entries](http://msdn.microsoft.com/ko-kr/948ff920-a739-4e66-a191-ee951512d42c)   
 [How to: Remove an Event Source](http://msdn.microsoft.com/ko-kr/bc66c900-4b8a-426a-b8e2-17031a20167e)