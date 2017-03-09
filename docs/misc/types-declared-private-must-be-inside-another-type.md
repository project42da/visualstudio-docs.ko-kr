---
title: "&#39;Private&#39;으로 선언된 형식은 다른 형식의 내부에 있어야 합니다. | Microsoft Docs"
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
  - "vbc31089"
  - "bc31089"
helpviewer_keywords: 
  - "BC31089"
ms.assetid: 44ea5fe4-4af6-4cea-a4a5-2cf966df2937
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Private&#39;으로 선언된 형식은 다른 형식의 내부에 있어야 합니다.
`Private` 한정자가 다른 형식에 포함되지 않은 형식에서 사용되었습니다.  
  
 **오류 ID:** BC31089  
  
### 이 오류를 해결하려면  
  
1.  `Friend`와 같은 덜 제한적인 액세스 한정자를 사용합니다.  
  
2.  다른 형식 내에서 형식을 선언합니다.  
  
## 참고 항목  
 [Private](/dotnet/visual-basic/language-reference/modifiers/private)