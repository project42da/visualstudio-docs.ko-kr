---
title: "&#39;If&#39;, &#39;ElseIf&#39;, &#39;Else&#39;, &#39;End If&#39; 또는 &#39;Const&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc30248"
  - "bc30248"
helpviewer_keywords: 
  - "BC30248"
ms.assetid: fa3bf591-8036-459c-8c29-ed7784e444f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;If&#39;, &#39;ElseIf&#39;, &#39;Else&#39;, &#39;End If&#39; 또는 &#39;Const&#39;가 필요합니다.
소스 줄이 `#` 문자로 시작되지만 유효한 조건부 컴파일 지시문이 `#` 바로 뒤에 오지 않습니다. 유효한 지시문에 `#Const`, `#ExternalSource`, `#If`, `#Else`, `#ElseIf`, `#End If` 및 `#Region`이 포함됩니다.  
  
 **오류 ID:** BC30248  
  
### 이 오류를 해결하려면  
  
1.  조건부 컴파일 지시문의 철자가 올바른지 확인합니다.  
  
2.  `#` 문자와 지시문 사이에 공백이 없는지 확인합니다.  
  
3.  `#` 문자를 제거하거나 올바른 지시문을 바로 뒤에 추가합니다.  
  
## 참고 항목  
 [Directives](/dotnet/visual-basic/language-reference/directives/directives)