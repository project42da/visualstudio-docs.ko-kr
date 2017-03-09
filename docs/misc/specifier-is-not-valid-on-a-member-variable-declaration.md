---
title: "&#39;&lt;specifier&gt;&#39;는 멤버 변수 선언에서 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30235"
  - "bc30235"
helpviewer_keywords: 
  - "BC30235"
ms.assetid: 8c5764e4-0096-4ca0-8656-05341a39833a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;specifier&gt;&#39;는 멤버 변수 선언에서 사용할 수 없습니다.
`Dim` 문에 잘못된 키워드가 포함되어 있습니다.`Dim` 문에는 `Friend`, `Private`, `Protected`, `Public`, `ReadOnly`, `Shadows`, `Shared` 또는 `Static` 키워드만 포함할 수 있습니다.  
  
 이 메시지는 프로시저 밖에서 `Static` 변수를 선언한 경우에도 나타날 수 있습니다.`Static`은 프로시저 수준에서만 사용할 수 있습니다.  
  
 `Dim` 문에 유효한 키워드를 포함한 경우 `Dim` 키워드를 선택적으로 생략할 수 있습니다.  
  
 **오류 ID:** BC30235  
  
### 이 오류를 해결하려면  
  
1.  `Dim` 문에서 잘못된 키워드를 제거합니다.  
  
2.  프로시저 밖에서 `Static` 변수를 선언한 경우 선언을 프로시저 안으로 이동하거나 `Static` 키워드를 제거합니다.  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)