---
title: "&#39;&lt;eventname&gt;&#39;은 &lt;type&gt; &#39;&lt;typename&gt;&#39;에서 암시적으로 선언되는 멤버와 충돌하는 &#39;&lt;membername&gt;&#39;을 암시적으로 정의합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31059"
  - "vbc31059"
helpviewer_keywords: 
  - "BC31059"
ms.assetid: 60ddb2f4-a204-41eb-b13b-b2bb13ddb69c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39;은 &lt;type&gt; &#39;&lt;typename&gt;&#39;에서 암시적으로 선언되는 멤버와 충돌하는 &#39;&lt;membername&gt;&#39;을 암시적으로 정의합니다.
형식 멤버의 이름이 이벤트에 대해 암시적으로 만든 멤버 이름과 충돌합니다. 이벤트가 암시적으로 여러 변수를 만듭니다. 예를 들어 선언 `Event X`가 암시적으로 이름 `XEventHandler`, `XEvent`, `add_X` 및 `remove_X`를 선언합니다.  
  
 **오류 ID:** BC31059  
  
### 이 오류를 해결하려면  
  
-   이름 충돌을 제거하려면 명시적으로 선언된 멤버 이름을 바꿉니다.  
  
## 참고 항목  
 [NotInBuild:Visual Basic의 선언문](http://msdn.microsoft.com/ko-kr/81f3c398-f45c-4d95-80bf-aa39d1a0fb30)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)