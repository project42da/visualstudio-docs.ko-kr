---
title: "&#39;On Error&#39; 문은 &#39;SyncLock&#39; 문 안에서 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30752"
  - "vbc30752"
helpviewer_keywords: 
  - "BC30752"
ms.assetid: 5c726627-b0fc-4edf-bd29-a83a0009f44d
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;On Error&#39; 문은 &#39;SyncLock&#39; 문 안에서 사용할 수 없습니다.
`On Error` 문은 스레드 동기화를 방해하기 때문에 `SyncLock` 블록에서 사용될 수 없습니다.  
  
 **오류 ID:** BC30752  
  
### 이 오류를 해결하려면  
  
1.  `SyncLock` 블록 밖에 `On Error` 문을 배치합니다.  
  
## 참고 항목  
 [On Error Statement](/dotnet/visual-basic/language-reference/statements/on-error-statement)