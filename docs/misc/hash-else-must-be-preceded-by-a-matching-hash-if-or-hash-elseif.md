---
title: "&#39;#Else&#39;는 짝이 맞는 &#39;#If&#39; 또는 &#39;#ElseIf&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30028"
  - "bc30028"
helpviewer_keywords: 
  - "BC30028"
ms.assetid: c6ed34de-d6ed-4227-9880-538055aff20a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#Else&#39;는 짝이 맞는 &#39;#If&#39; 또는 &#39;#ElseIf&#39; 뒤에 와야 합니다.
`#Else`는 조건부 컴파일 지시문입니다.`#Else` 지시문 앞에 해당 `#If` 또는 `#ElseIf` 지시문이 없습니다.  
  
 **오류 ID:** BC30028  
  
### 이 오류를 해결하려면  
  
1.  간섭 조건부 컴파일 블록 또는 잘못 배치된 `#End If`에 의해 앞에 오는 `#If` 또는 `#ElseIf`가 이 `#Else`와 분리되지 않았는지 확인합니다.  
  
2.  `#Else` 앞에 다른 `#Else` 지시문이 있는지 확인합니다. 있는 경우 `#Else`를 제거하거나 `#ElseIf`로 변경합니다.  
  
3.  다른 모든 항목의 순서가 올바른 경우 `#If` 지시문을 조건부 컴파일 블록의 시작 부분에 추가합니다.  
  
## 참고 항목  
 [\#If...Then...\#Else Directives](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)