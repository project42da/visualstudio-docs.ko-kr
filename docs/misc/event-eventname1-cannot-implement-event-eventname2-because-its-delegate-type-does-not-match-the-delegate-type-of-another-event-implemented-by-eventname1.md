---
title: "대리자 형식이 &#39;&lt;eventname1&gt;&#39;에 의해 구현된 다른 이벤트의 대리자 형식과 일치하지 않으므로 &#39;&lt;eventname1&gt;&#39; 이벤트에서 &#39;&lt;eventname2&gt;&#39; 이벤트를 구현할 수 없습니다. | Microsoft Docs"
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
  - "bc31407"
  - "vbc31407"
helpviewer_keywords: 
  - "BC31407"
ms.assetid: 0b9ffddb-4759-438b-b569-beac7062e986
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 대리자 형식이 &#39;&lt;eventname1&gt;&#39;에 의해 구현된 다른 이벤트의 대리자 형식과 일치하지 않으므로 &#39;&lt;eventname1&gt;&#39; 이벤트에서 &#39;&lt;eventname2&gt;&#39; 이벤트를 구현할 수 없습니다.
이벤트의 대리자 형식이 다른 이벤트의 대리자 형식과 일치하지 않으므로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 이벤트를 구현할 수 없습니다. 이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다. 구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.  
  
 **오류 ID:** BC31407  
  
### 이 오류를 해결하려면  
  
-   이벤트를 개별적으로 구현합니다.  
  
## 참고 항목  
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)