---
title: "&lt;type1&gt; &#39;&lt;typename1&gt;&#39;은 &lt;type2&gt; &#39;&lt;typename2&gt;&#39;의 event &#39;&lt;eventname&gt;&#39;에 대해 암시적으로 선언된 멤버와 충돌합니다. | Microsoft Docs"
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
  - "vbc31061"
  - "bc31061"
helpviewer_keywords: 
  - "BC31061"
ms.assetid: de5b1121-8c8f-4aba-a3e7-1e3e60df0dc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;typename1&gt;&#39;은 &lt;type2&gt; &#39;&lt;typename2&gt;&#39;의 event &#39;&lt;eventname&gt;&#39;에 대해 암시적으로 선언된 멤버와 충돌합니다.
형식 멤버의 이름이 이벤트에 대해 암시적으로 만든 멤버 이름과 충돌합니다. 이벤트가 암시적으로 여러 암시적 변수를 만듭니다. 예를 들어 선언 `Event X`가 암시적으로 이름 `XEventHandler`, `XEvent`, `add_X` 및 `remove_X`를 선언합니다.  
  
 **오류 ID:** BC31061  
  
### 이 오류를 해결하려면  
  
-   이름 충돌을 제거하려면 명시적으로 선언된 멤버 이름을 바꿉니다.  
  
## 참고 항목  
 [NotInBuild:Visual Basic의 선언문](http://msdn.microsoft.com/ko-kr/81f3c398-f45c-4d95-80bf-aa39d1a0fb30)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)