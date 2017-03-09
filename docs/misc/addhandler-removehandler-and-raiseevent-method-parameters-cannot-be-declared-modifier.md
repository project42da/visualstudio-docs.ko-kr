---
title: "&#39;AddHandler&#39;, &#39;RemoveHandler&#39; 및 &#39;RaiseEvent&#39; 메서드 매개 변수는 &#39;&lt;modifier&gt;&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc31138"
  - "bc31138"
helpviewer_keywords: 
  - "BC31138"
ms.assetid: 6d8df92a-95fc-4a7d-ab1e-06d312155c55
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 및 &#39;RaiseEvent&#39; 메서드 매개 변수는 &#39;&lt;modifier&gt;&#39;로 선언할 수 없습니다.
`AddHandler`, `RemoveHandler` 및 `RaiseEvent` 메서드의 매개 변수는 `Optional` 또는 `ParamArray` 한정자로 선언할 수 없습니다.  
  
 `Optional` 또는 `ParamArray` 한정자는 `Declare`, `Function`, `Property` 및 `Sub` 선언의 매개 변수에만 사용할 수 있습니다.  
  
 **오류 ID:** BC31138  
  
### 이 오류를 해결하려면  
  
-   매개 변수 목록에서 `Optional` 또는 `ParamArray` 키워드를 제거합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional)   
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)