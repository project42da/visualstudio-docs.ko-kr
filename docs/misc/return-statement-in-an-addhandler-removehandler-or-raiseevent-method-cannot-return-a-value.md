---
title: "&#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드의 &#39;Return&#39; 문은 값을 반환할 수 없습니다. | Microsoft Docs"
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
  - "bc30940"
  - "vbc30940"
helpviewer_keywords: 
  - "BC30940"
ms.assetid: 0e4d037a-2d20-40e4-8ead-6d709d1c9c7a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드의 &#39;Return&#39; 문은 값을 반환할 수 없습니다.
`Custom Event` 선언의 `AddHandler`, `RemoveHandler` 및 `RaiseEvent` 메서드는 `Return` 문을 포함하여 메서드를 종료할 수 있습니다. 그러나 메서드가 값을 반환할 수 없으므로 `Return` 문에서 반환 값을 지정할 수 없습니다.  
  
 **오류 ID:** BC30940  
  
### 이 오류를 해결하려면  
  
-   `Return` 문 뒤에 있는 식을 제거합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [Return Statement](/dotnet/visual-basic/language-reference/statements/return-statement)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)