---
title: "&#39;Assembly&#39; 또는 &#39;Module&#39;이 필요합니다. | Microsoft Docs"
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
  - "vbc32015"
  - "bc32015"
helpviewer_keywords: 
  - "BC32015"
ms.assetid: 6e62fe8d-a875-4995-b6b2-443e75c65e85
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Assembly&#39; 또는 &#39;Module&#39;이 필요합니다.
전역 특성은 전체 어셈블리에 적용되는지 또는 현재 모듈에만 적용되는지를 표시하지 않고 지정됩니다. 전역 특성은 `Assembly` 또는 `Module` 중 하나를 지정해야 합니다.  
  
 전역 특성은 특정 프로그래밍 요소의 선언에 적용되지 않고 소스 줄 자체에 표시되는 특성입니다.  
  
 **오류 ID:** BC32015  
  
### 이 오류를 해결하려면  
  
1.  특성을 전역으로 지정하려는 경우 특성 블록의 시작 부분에 `Assembly` 또는 `Module` 키워드와 콜론\(:\)을 추가합니다.  
  
2.  특성을 전역으로 지정하지 않으려는 경우 특성 블록을 삭제하거나 프로그래밍 요소 선언으로 이동합니다.  
  
## 참고 항목  
 [Assembly](/dotnet/visual-basic/language-reference/modifiers/assembly)   
 [Module \<keyword\>](../Topic/Module%20%3Ckeyword%3E%20\(Visual%20Basic\).md)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [빌드에 없음: Visual Basic의 전역 특성](http://msdn.microsoft.com/ko-kr/253a32d8-1531-4504-b687-088554ab71d2)