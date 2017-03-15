---
title: "&#39;Life&#39; 인수는 0일 수 없습니다. | Microsoft Docs"
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
  - "vbrFinancial_LifeNEZero"
ms.assetid: c402da97-a2b2-4219-a83a-0cebbfdffef2
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Life&#39; 인수는 0일 수 없습니다.
자산의 내용 연수 길이를 지정하는 `Double`이어야 하는 `Life`에 대한 인수가 잘못되었습니다.  
  
### 이 오류를 해결하려면  
  
-   식에서 인수의 철자를 검사합니다. 철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.  
  
-   이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.  
  
## 참고 항목  
 [빌드에 없음: DDB 함수](http://msdn.microsoft.com/ko-kr/c7cf8929-d158-4399-b3cb-31d897d12556)   
 [빌드에 없음: SYD 함수](http://msdn.microsoft.com/ko-kr/23c25672-f5dd-49ac-9893-4faa82634181)   
 [빌드에 없음: SLN 함수](http://msdn.microsoft.com/ko-kr/8e06130a-056e-4266-a8a9-1592b86f58d2)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)