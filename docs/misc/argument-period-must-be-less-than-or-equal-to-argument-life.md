---
title: "&#39;Period&#39; 인수는 &#39;Life&#39; 인수보다 작거나 같아야 합니다. | Microsoft Docs"
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
  - "vbrFinancial_PeriodLELife"
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Period&#39; 인수는 &#39;Life&#39; 인수보다 작거나 같아야 합니다.
자산 감가상각이 계산되는 기간을 지정하는 `Period` 인수 값이 `Life` 인수 값보다 큽니다.  
  
### 이 오류를 해결하려면  
  
-   `Life`와 `Period` 인수는 같은 단위로 표현되어야 합니다. 예를 들어 `Life`가 월 단위로 측정되면 `Period`도 월 단위로 측정되어야 합니다.  
  
## 참고 항목  
 [빌드에 없음: DDB 함수](http://msdn.microsoft.com/ko-kr/c7cf8929-d158-4399-b3cb-31d897d12556)   
 [빌드에 없음: SYD 함수](http://msdn.microsoft.com/ko-kr/23c25672-f5dd-49ac-9893-4faa82634181)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)