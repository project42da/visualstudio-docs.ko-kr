---
title: "&#39;AddHandler&#39;, &#39;RemoveHandler&#39; 및 &#39;RaiseEvent&#39; 메서드에는 지정자를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31135"
  - "bc31135"
helpviewer_keywords: 
  - "BC31135"
ms.assetid: 2eaf5a6f-d201-4f9b-bcdf-12170cb44791
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 및 &#39;RaiseEvent&#39; 메서드에는 지정자를 사용할 수 없습니다.
`AddHandler`, `RemoveHandler` 및 `RaiseEvent` 메서드 선언은 `Public` 또는 `ReadOnly`와 같은 키워드로 수정할 수 없습니다. 수정할 수 있는 선언만 이러한 키워드를 포함할 수 있습니다.  
  
 **오류 ID:** BC31135  
  
### 이 오류를 해결하려면  
  
-   메서드 선언에서 키워드를 제거합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [NIB 키워드\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/3a6fda51-6ade-4862-a407-1c305c3906ec)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)