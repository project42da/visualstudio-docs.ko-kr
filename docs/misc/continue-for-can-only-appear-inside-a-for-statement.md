---
title: "&#39;Continue For&#39;는 &#39;For&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc30783"
  - "vbc30783"
helpviewer_keywords: 
  - "BC30783"
ms.assetid: 70891018-27c8-4d36-b168-8cc7177d70cb
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Continue For&#39;는 &#39;For&#39; 문 내부에만 사용할 수 있습니다.
`Continue For` 문은 `For...Next` 루프 내에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC30783  
  
### 이 오류를 해결하려면  
  
1.  `Continue For` 문이 `Do...Loop`에 있는 경우 해당 문을 `Continue Do`로 변경합니다.  
  
     또는  
  
     `Continue For` 문이 `While...End While` 루프에 있는 경우 해당 문을 `Continue While`로 변경합니다.  
  
2.  그렇지 않으면 `Continue For` 문을 제거합니다.  
  
## 참고 항목  
 [Continue Statement](/dotnet/visual-basic/language-reference/statements/continue-statement)   
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)