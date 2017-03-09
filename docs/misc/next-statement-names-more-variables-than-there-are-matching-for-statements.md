---
title: "&#39;Next&#39; 문은 해당 &#39;For&#39; 문에 있는 변수보다 많은 변수를 명명합니다. | Microsoft Docs"
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
  - "bc32037"
  - "vbc32037"
helpviewer_keywords: 
  - "BC32037"
ms.assetid: 7c97d835-1043-40ec-a645-63a053f5f916
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Next&#39; 문은 해당 &#39;For&#39; 문에 있는 변수보다 많은 변수를 명명합니다.
다음 예제와 같이 중첩된 루프가 중첩에 있는 루프보다 많은 루프 변수를 지정하는 단일 `Next` 문으로 종료되었습니다.  
  
```  
For I = 1 To 10 For J = 1 To 5 ' ... Next J, I, K   ' Next J, I is valid, but there is no loop on K.  
```  
  
 **오류 ID:** BC32037  
  
### 이 오류를 해결하려면  
  
1.  `Next` 문이 중첩된 모든 루프 변수를 루프 시작의 역순으로 지정하는지 확인합니다.  
  
2.  `Next` 문에서 불필요한 변수를 모두 제거합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)