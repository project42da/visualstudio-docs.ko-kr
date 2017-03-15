---
title: "특성에 Public 생성자가 없으므로 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30758"
  - "bc30758"
helpviewer_keywords: 
  - "BC30758"
ms.assetid: b72d1ff2-f6b2-4a89-9ac2-8765f77bcc97
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성에 Public 생성자가 없으므로 사용할 수 없습니다.
사용할 특성에 대한 생성자는 `Private`이며 사용할 수 없습니다.  
  
 **오류 ID:** BC30758  
  
### 이 오류를 해결하려면  
  
1.  이 오류가 개발한 사용자 지정 특성에서 나타나면 `Sub``New` 생성자의 액세스 한정자를 `Public`으로 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)