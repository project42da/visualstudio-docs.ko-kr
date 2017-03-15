---
title: "&#39;Exit AddHandler&#39;, &#39;Exit RemoveHandler&#39; 및 &#39;Exit RaiseEvent&#39;가 잘못되었습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31111"
  - "bc31111"
helpviewer_keywords: 
  - "BC31111"
ms.assetid: e02264f3-0645-4de5-b622-8a2a74496b64
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit AddHandler&#39;, &#39;Exit RemoveHandler&#39; 및 &#39;Exit RaiseEvent&#39;가 잘못되었습니다.
'Exit AddHandler', 'Exit RemoveHandler' 및 'Exit RaiseEvent'가 잘못되었습니다. 이벤트 멤버에서 나오려면 'Return'을 사용하세요.  
  
 `Exit` 문은 `Custom Event` 선언의 `AddHandler`, `RemoveHandler` 또는 `RaiseEvent` 메서드를 종료하기 위해 사용될 수 없습니다. 대신 반환 식을 지정하지 않고 `Return` 문을 사용하여 메서드를 종료합니다.  
  
 **오류 ID:** BC31111  
  
### 이 오류를 해결하려면  
  
-   `Exit` 문을 `Return` 문으로 바꿉니다.  
  
     `Return` 문이 반환 식을 지정하지 않는지 확인합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [Return Statement](/dotnet/visual-basic/language-reference/statements/return-statement)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)