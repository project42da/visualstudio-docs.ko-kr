---
title: "Alias definition is recursive. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A00DA"
  - "vs.message.VS_E_RECURSIVEALIAS"
ms.assetid: e48a2908-9b94-4c6a-9807-beeeba71531c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Alias definition is recursive.
이 오류는 자신을 직접 또는 간접적으로 참조하는 별칭을 정의하는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  별칭 정의를 변경하고 다시 시도하십시오.  
  
     — 또는 —  
  
2.  **명령** 창에 `>alias`를 입력하여 현재 별칭 목록 및 해당 정의를 검토한 후 다시 시도합니다.  
  
## 참고 항목  
 [별칭 명령](../ide/reference/alias-command.md)   
 [Visual Studio 명령 별칭](../ide/reference/visual-studio-command-aliases.md)