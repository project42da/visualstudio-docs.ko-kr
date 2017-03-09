---
title: "&#39;#ElseIf&#39;, &#39;#Else&#39; 또는 &#39;#End If&#39;는 짝이 되는 &#39;#If&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc30013"
  - "bc30013"
helpviewer_keywords: 
  - "BC30013"
ms.assetid: 8fe2d23c-8b8f-46d8-90f2-7f8857ea43bb
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#ElseIf&#39;, &#39;#Else&#39; 또는 &#39;#End If&#39;는 짝이 되는 &#39;#If&#39; 뒤에 와야 합니다.
`#ElseIf`, `#Else` 및 `#End If`는 조건부 컴파일 지시문입니다.`#ElseIf`, `#Else` 또는 `#End If`는 해당 `#If` 지시문 앞에 오지 않습니다.  
  
 **오류 ID:** BC30013  
  
### 이 오류를 해결하려면  
  
1.  간섭 조건부 컴파일 블록 또는 잘못 배치된 `#End If`에 의해 의도한 `#If`가 문제가 있는 절과 분리되지 않았는지 확인합니다.  
  
    > [!NOTE]
    >  `#If` 블록마다 `#Else`가 하나만 허용되므로 두 개의 연속 `#Else` 지시문이 있으면 이 오류가 발생합니다.  
  
2.  선행 `#`이 이전의 `#If` 지시문에서 누락되지 않았는지 확인합니다.  
  
3.  다른 모든 항목의 순서가 올바른 경우 `#If` 지시문을 조건부 컴파일 블록의 시작 부분에 추가합니다.  
  
## 참고 항목  
 [\#If...Then...\#Else Directives](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)