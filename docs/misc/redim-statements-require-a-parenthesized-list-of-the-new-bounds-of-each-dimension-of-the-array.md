---
title: "&#39;ReDim&#39; 문에는 배열의 각 차원에 대한 괄호로 묶인 새 범위 목록이 필요합니다. | Microsoft Docs"
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
  - "bc30670"
  - "vbc30670"
helpviewer_keywords: 
  - "BC30670"
ms.assetid: b2c5fea3-e7db-4797-b917-d61a65befbd4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReDim&#39; 문에는 배열의 각 차원에 대한 괄호로 묶인 새 범위 목록이 필요합니다.
배열의 새 크기를 `ReDim` 문의 일부로 지정해야 합니다.  
  
 **오류 ID:** BC30670  
  
### 이 오류를 해결하려면  
  
-   해당 배열의 각 차수 크기를 제공해야 합니다. 예를 들어 다음과 같습니다.  
  
    ```  
    ReDim arr(5, 6)  
    ```  
  
## 참고 항목  
 [ReDim Statement](/dotnet/visual-basic/language-reference/statements/redim-statement)