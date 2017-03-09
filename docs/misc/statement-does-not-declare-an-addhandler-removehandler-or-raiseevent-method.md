---
title: "문에서 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드를 선언하지 않았습니다. | Microsoft Docs"
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
  - "vbc31113"
  - "bc31113"
helpviewer_keywords: 
  - "BC31113"
ms.assetid: f8299c9d-6030-43e5-878e-8d2b042191b5
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 문에서 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드를 선언하지 않았습니다.
문이 `Custom Event` 프로시저에서 `AddHandler`, `RemoveHandler` 또는 `RaiseEvent` 선언문을 제공하지 않습니다. 사용자 지정 이벤트 선언은 `Custom Event`과 `End Event` 문으로 둘러 싸인 코드 블록입니다. 이 블록에서 각 `Custom Event` 프로시저는 선언문과 `End` 문으로 둘러 싸인 내부 블록으로 표시됩니다.  
  
 **오류 ID:** BC31113  
  
### 이 오류를 해결하려면  
  
-   `AddHandler`, `RemoveHandler` 또는 `RaiseEvent` 선언문을 제공합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)