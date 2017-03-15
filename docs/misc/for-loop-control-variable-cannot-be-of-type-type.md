---
title: "&#39;For&#39; 루프 제어 변수는 &#39;&lt;type&gt;&#39; 형식일 수 없습니다. | Microsoft Docs"
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
  - "vbc30337"
  - "bc30337"
helpviewer_keywords: 
  - "BC30337"
ms.assetid: 988bba15-e9a2-4045-98a0-7f53c8b2c3e3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;For&#39; 루프 제어 변수는 &#39;&lt;type&gt;&#39; 형식일 수 없습니다.
유효한 형식이 아닌 루프 제어 변수를 사용하려고 했습니다.`For` 루프의 맨 앞에서 시작점, 끝점 및 단계 값이 텍스트 순서대로 평가됩니다. 세 개의 식을 모두 암시적으로 변수 형식으로 변환해야 합니다.`For` 루프 변수가 `Object` 형식이면 런타임에 식 중 하나 이상이 숫자 형식이어야 하며, 세 개의 식을 모두 가장 넓은 숫자 형식으로 강제 변환해야 합니다.  
  
 **오류 ID:** BC30337  
  
### 이 오류를 해결하려면  
  
-   루프 제어 변수의 형식을 확인하고 유효한 형식으로 변경합니다.  
  
## 참고 항목  
 [Visual Basic의 경우](http://msdn.microsoft.com/ko-kr/c470a263-9b49-4308-8fd6-8592b84a7980)   
 [Do...Loop Statement](/dotnet/visual-basic/language-reference/statements/do-loop-statement)   
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)