---
title: "&#39;#ElseIf&#39;는 &#39;&#39;#If&#39; 블록의 일부로 &#39;#Else&#39; 뒤에 올 수 없습니다. | Microsoft Docs"
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
  - "bc32030"
  - "vbc32030"
helpviewer_keywords: 
  - "BC32030"
ms.assetid: 248d6464-3019-4753-8a33-7070bbe5d2a6
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#ElseIf&#39;는 &#39;&#39;#If&#39; 블록의 일부로 &#39;#Else&#39; 뒤에 올 수 없습니다.
`#ElseIf` 조건부 컴파일 지시문은 `#Else` 지시문 뒤에 옵니다.`#Else`는 `#End If` 지시문 앞에서 조건부 블록의 마지막 지시문이어야 합니다.  
  
 **오류 ID:** BC32030  
  
### 이 오류를 해결하려면  
  
1.  앞의 `#Else`가 `#ElseIf`이어야 하는지 확인합니다.  
  
2.  앞의 `#If` 블록이 올바르게 종료되고 새 `#If` 블록이 시작되었는지 확인합니다.  
  
3.  다른 모든 항목이 올바르면 이 `#ElseIf` 지시문과 해당 문 블록이 `#Else` 블록 앞에 오도록 이동합니다.  
  
## 참고 항목  
 [\#If...Then...\#Else Directives](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)