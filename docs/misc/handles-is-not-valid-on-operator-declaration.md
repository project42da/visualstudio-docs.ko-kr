---
title: "연산자 선언에는 &#39;Handles&#39;를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc33003"
  - "vbc33003"
helpviewer_keywords: 
  - "BC33003"
ms.assetid: 8336402c-9393-4e8e-834d-55c2268f24f6
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연산자 선언에는 &#39;Handles&#39;를 사용할 수 없습니다.
[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)은 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause) 키워드를 지정합니다.  
  
 `Sub` 프로시저만 이벤트를 처리할 수 있습니다.`Operator` 프로시저는 처리할 수 없습니다. 이벤트 처리기에 대한 자세한 내용은 [How to: Call an Event Handler in Visual Basic](../Topic/How%20to:%20Call%20an%20Event%20Handler%20in%20Visual%20Basic.md)을 참조하세요.  
  
 `Operator` 프로시저에는 `Public` 및 `Shared` 키워드가 모두 필요하며 변환 연산자에는 `Widening` 또는 `Narrowing` 키워드가 필요합니다. 자세한 내용은 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)을 참조하세요.  
  
 **오류 ID:** BC33003  
  
### 이 오류를 해결하려면  
  
-   이 프로시저에서 이벤트를 처리하도록 하려면 `Sub` 프로시저로 다시 작성합니다.  
  
-   이 프로시저가 연산자를 정의하려면 프로시저의 선언에서 `Handles` 키워드를 제거합니다.  
  
## 참고 항목  
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)