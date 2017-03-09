---
title: "&#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드 매개 변수는 &#39;ByRef&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc31134"
  - "bc31134"
helpviewer_keywords: 
  - "BC31134"
ms.assetid: 942f0b91-e71a-499a-ad10-a5dfcb4e72b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드 매개 변수는 &#39;ByRef&#39;로 선언할 수 없습니다.
`AddHandler` 및 `RemoveHandler` 메서드의 매개 변수는 `ByRef` 한정자로 선언할 수 없습니다.  
  
 **오류 ID:** BC31134  
  
### 이 오류를 해결하려면  
  
-   매개 변수에서 `ByRef` 키워드를 제거합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [ByRef](/dotnet/visual-basic/language-reference/modifiers/byref)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)