---
title: "&#39;&lt;method&gt;&#39;는 &#39;&lt;modifier&gt;&#39;이므로 이 컨텍스트에서 액세스할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30389"
  - "bc30389"
helpviewer_keywords: 
  - "BC30389"
ms.assetid: fae58a68-df91-4741-a8c9-f1bb10e166e2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;method&gt;&#39;는 &#39;&lt;modifier&gt;&#39;이므로 이 컨텍스트에서 액세스할 수 없습니다.
`Private`으로 선언되었으므로 이 컨텍스트에서 액세스할 수 없는 메서드에 액세스하려고 했습니다. 이 오류는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러가 클래스의 모든 멤버를 가져오고 대\/소문자를 구분하지 않아서 발생할 수 있으므로 이름을 대\/소문자로만 구별하면 충돌할 수 있습니다.  
  
 **오류 ID:** BC30389  
  
### 이 오류를 해결하려면  
  
-   메서드 `Public`을 선언하는 것이 좋습니다.  
  
-   이름이 충돌하여 오류가 발생하는 경우 충돌하는 이름에 대\/소문자 이외의 다른 점을 지정합니다.  
  
## 참고 항목  
 [Private](/dotnet/visual-basic/language-reference/modifiers/private)