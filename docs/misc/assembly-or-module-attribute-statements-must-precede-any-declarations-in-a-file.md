---
title: "어셈블리 또는 모듈 특성 문은 파일의 모든 선언 앞에 와야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30637"
  - "bc30637"
helpviewer_keywords: 
  - "BC30637"
ms.assetid: 80242581-fa8a-4903-9395-6f7ad1610231
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 어셈블리 또는 모듈 특성 문은 파일의 모든 선언 앞에 와야 합니다.
전역 특성은 소스 파일 맨 위의 `Option` 및 `Imports` 문 뒤, 다른 문 앞에서 선언해야 합니다.  
  
 **오류 ID:** BC30637  
  
### 이 오류를 해결하려면  
  
1.  `<Module:>` 및 `<Assembly:>`와 같은 전역 특성을 소스 파일 맨 위에 배치합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [빌드에 없음: Visual Basic의 전역 특성](http://msdn.microsoft.com/ko-kr/253a32d8-1531-4504-b687-088554ab71d2)