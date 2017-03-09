---
title: "&#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드에는 매개 변수를 하나만 사용해야 합니다. | Microsoft Docs"
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
  - "vbc31133"
  - "bc31133"
helpviewer_keywords: 
  - "BC31133"
ms.assetid: f6295626-dd63-408c-ab5f-76367f94d6ca
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드에는 매개 변수를 하나만 사용해야 합니다.
사용자 지정 이벤트 선언에 각 선언이 사용자 지정 이벤트 `As` 절에 의해 지정되는 대리자 형식의 단일 매개 변수를 사용하는 `AddHandler` 또는 `RemoveHandler` 선언이 있어야 합니다.  
  
 **오류 ID:** BC31133  
  
### 이 오류를 해결하려면  
  
-   매개 변수 목록에서 불필요한 매개 변수를 제거하고 매개 변수 형식을 사용자 지정 이벤트의 `As` 절에서 지정된 대리자 형식과 동일하게 변경합니다.  
  
## 예제  
 이 예제에서는 `AddHandler` 및 `RemoveHandler` 선언에 대한 올바른 매개 변수 형식으로 사용자 지정 이벤트를 보여 줍니다.  
  
 [!CODE [VbVbalrEventError#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#1)]  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)