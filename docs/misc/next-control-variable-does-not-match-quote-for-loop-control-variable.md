---
title: "&#39;Next&#39; 제어 변수가 &#39;For&#39; 루프 제어 변수와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc30976"
  - "bc30976"
helpviewer_keywords: 
  - "BC30976"
ms.assetid: 87c2d464-43bf-426f-b78b-7bc07ba171e6
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Next&#39; 제어 변수가 &#39;For&#39; 루프 제어 변수와 일치하지 않습니다.
`For...Next` 루프의 `Next` 문에 있는 제어 변수는 해당 `For` 문의 변수와 일치해야 합니다.  
  
 **오류 ID:** BC30976  
  
### 이 오류를 해결하려면  
  
-   `Next` 문 및 해당 `For` 문에 있는 변수의 철자가 일치하는지 확인합니다.  
  
-   바깥쪽 루프의 일부가 실수로 삭제되지 않았는지 확인합니다.  
  
-   이 루프가 중첩된 루프 집합의 일부인 경우 모든 루프가 올바르게 종료되는지 확인합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)