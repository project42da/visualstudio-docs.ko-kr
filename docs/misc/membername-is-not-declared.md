---
title: "&#39;&lt;membername&gt;&#39;이 선언되지 않았습니다. | Microsoft Docs"
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
  - "vbc30816"
  - "bc30816"
helpviewer_keywords: 
  - "BC30816"
ms.assetid: d6704bed-bb76-47c6-ac28-09608d5e6912
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39;이 선언되지 않았습니다.
'`<membername>`'이\(가\) 선언되지 않았습니다.`Debug` 개체 기능은 `System` 어셈블리의 `System.Diagnostics.Debug`에서 사용할 수 있습니다.  
  
 지정된 멤버 이름을 찾을 수 없습니다.  
  
 **오류 ID:** BC30816  
  
### 이 오류를 해결하려면  
  
1.  멤버의 철자를 확인합니다.  
  
2.  `Imports` 문 또는 다른 네임스페이스에 정의된 정규화된 멤버를 사용합니다. 예를 들어 `WriteLine` 함수는 `System.Diagnostics.Debug` 네임스페이스에서 선언됩니다.  
  
## 참고 항목  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)