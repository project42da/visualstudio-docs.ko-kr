---
title: "&#39;Select Case&#39;와 첫 번째 &#39;Case&#39; 사이에는 문 및 레이블을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30058"
  - "vbc30058"
helpviewer_keywords: 
  - "BC30058"
ms.assetid: 399b4659-f7df-4377-80be-43019f1e6206
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Select Case&#39;와 첫 번째 &#39;Case&#39; 사이에는 문 및 레이블을 사용할 수 없습니다.
`Select` 또는 `Select Case` 문과 첫 번째 `Case` 문 사이에 주석이 아닌 문을 사용했습니다.  
  
 **오류 ID:** BC30058  
  
### 이 오류를 해결하려면  
  
-   간섭 문이 주석인 경우 앞에 주석 구분 기호\(`'` 또는 `REM`\)를 추가합니다. 그렇지 않으면 문을 이동하거나 삭제합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)