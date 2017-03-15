---
title: "&#39;&lt;argumentname&gt;&#39; 인수의 범위는 1에서 255 사이여야 합니다. | Microsoft Docs"
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
  - "vbrArgument_Range1toFF1"
ms.assetid: a447f9a6-1c90-4c71-abff-81170331e4c5
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;argumentname&gt;&#39; 인수의 범위는 1에서 255 사이여야 합니다.
0에서 255 사이의 범위를 벗어나므로 인수가 올바르지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  식에서 인수의 철자를 검사합니다. 철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.  
  
2.  이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.  
  
## 참고 항목  
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)