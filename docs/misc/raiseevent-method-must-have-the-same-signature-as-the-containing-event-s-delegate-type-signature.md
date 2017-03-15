---
title: "&#39;RaiseEvent&#39; 메서드의 서명은 포함하는 이벤트의 대리자 형식 &#39;&lt;signature&gt;&#39;의 서명과 같아야 합니다. | Microsoft Docs"
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
  - "bc31137"
  - "vbc31137"
helpviewer_keywords: 
  - "BC31137"
ms.assetid: 9db77546-9205-4fd2-baf6-6eb1b46b1f1a
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;RaiseEvent&#39; 메서드의 서명은 포함하는 이벤트의 대리자 형식 &#39;&lt;signature&gt;&#39;의 서명과 같아야 합니다.
`Custom Event` 선언에는 사용자 지정 이벤트의 `RaiseEvent` 절에서 지정된 대리자 형식과 동일한 서명을 가진 `As` 선언이 있어야 합니다.  
  
 서명이 일치하려면 `RaiseEvent` 선언과 대리자의 매개 변수 개수와 매개 변수 형식이 일치해야 합니다.  
  
 **오류 ID:** BC31137  
  
### 이 오류를 해결하려면  
  
-   `RaiseEvent` 선언의 매개 변수를 대리자 형식의 매개 변수와 일치하도록 변경합니다.  
  
## 예제  
 이 예제에서는 `RaiseEvent` 선언에 대한 올바른 매개 변수 형식으로 사용자 지정 이벤트를 보여 줍니다.  
  
 [!CODE [VbVbalrEventError#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#2)]  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)   
 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)