---
title: "스택의 맨 위에 없는 메서드에 대한 지역 변수 값을 설정할 수 없습니다. | Microsoft Docs"
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
  - "bc30711"
  - "vbc30711"
helpviewer_keywords: 
  - "BC30711"
ms.assetid: b2aa290f-3311-448a-af46-ff2a2add5788
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 스택의 맨 위에 없는 메서드에 대한 지역 변수 값을 설정할 수 없습니다.
변수가 호출 스택의 맨 위에 있는 경우에만 수정할 수 있습니다. 예를 들어 `procedure1`에서 `procedure2`를 호출했을 때 `procedure1`에 있는 경우 `procedure2`의 변수를 수정할 수 없습니다.  
  
 **오류 ID:** BC30711  
  
### 이 오류를 해결하려면  
  
-   호출 스택 맨 위의 변수를 수정합니다.  
  
## 참고 항목  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)