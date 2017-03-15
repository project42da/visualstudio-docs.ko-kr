---
title: "&#39;&lt;eventname&gt;&#39; 이벤트에 대한 &#39;RaiseEvent&#39; 정의가 없습니다. | Microsoft Docs"
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
  - "vbc31132"
  - "bc31132"
helpviewer_keywords: 
  - "BC31132"
ms.assetid: 8f3442fd-2ed1-4dbc-83a8-f0860ec022ac
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; 이벤트에 대한 &#39;RaiseEvent&#39; 정의가 없습니다.
이벤트가 `Custom`으로 선언된 경우 이벤트를 발생시키기 위한 프로시저를 제공해야 합니다.  
  
 **오류 ID:** BC31132  
  
### 이 오류를 해결하려면  
  
1.  `Custom Event` 문과 `End Event` 문 사이에 `RaiseEvent` 선언을 포함합니다.  
  
2.  이벤트 선언 내의 다른 프로시저가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [RaiseEvent Statement](/dotnet/visual-basic/language-reference/statements/raiseevent-statement)   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)