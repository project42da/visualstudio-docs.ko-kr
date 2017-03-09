---
title: "&#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드 매개 변수의 대리자 형식은 포함하는 이벤트의 대리자 형식과 같아야 합니다. | Microsoft Docs"
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
  - "bc31136"
  - "vbc31136"
helpviewer_keywords: 
  - "BC31136"
ms.assetid: 199b2f7b-a85e-465d-9853-0995156e7ab6
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39; 및 &#39;RemoveHandler&#39; 메서드 매개 변수의 대리자 형식은 포함하는 이벤트의 대리자 형식과 같아야 합니다.
`Custom Event` 선언에는 `AddHandler` 또는 `RemoveHandler` 선언이 있어야 하며, 각 선언은 사용자 지정 이벤트의 `As` 절에 의해 지정되는 대리자 형식의 단일 매개 변수를 갖습니다.  
  
 **오류 ID:** BC31136  
  
### 이 오류를 해결하려면  
  
-   사용자 지정 이벤트의 `As` 절에서 지정한 대리자 형식과 동일하게 매개 변수 형식을 변경합니다.  
  
## 예제  
 이 예제에서는 `AddHandler` 및 `RemoveHandler` 선언에 대한 올바른 매개 변수 형식으로 사용자 지정 이벤트를 보여 줍니다.  
  
 [!CODE [VbVbalrEventError#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#1)]  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)