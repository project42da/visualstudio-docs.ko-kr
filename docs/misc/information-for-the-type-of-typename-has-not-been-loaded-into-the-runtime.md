---
title: "&#39;&lt;typename&gt;&#39; 형식에 대한 정보가 런타임으로 로드되지 않았습니다. | Microsoft Docs"
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
  - "vbc30750"
  - "bc30750"
helpviewer_keywords: 
  - "BC30750"
ms.assetid: b0f074f9-571d-48f8-b334-4fd34b61cd89
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식에 대한 정보가 런타임으로 로드되지 않았습니다.
런타임에 의해 로드되지 않은 형식이 참조되었습니다.  
  
 **오류 ID:** BC30750  
  
### 이 오류를 해결하려면  
  
1.  현재 범위 내에서 형식이 정의되도록 코드를 재구성합니다.  
  
2.  멤버가 정의되고 멤버 이름을 올바르게 입력했는지 확인합니다.  
  
3.  모듈에 선언된 멤버 중 하나에 액세스해 봅니다. 선언된 모듈이 아직 로드되지 않아 디버깅 환경에서 멤버를 찾을 수 없는 경우도 있습니다.  
  
## 참고 항목  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)