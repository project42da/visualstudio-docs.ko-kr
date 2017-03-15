---
title: "상수 식이 필요합니다. | Microsoft Docs"
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
  - "bc30059"
  - "vbc30059"
helpviewer_keywords: 
  - "BC30059"
ms.assetid: fdd5e7bb-6370-4a63-bbb6-23b15badb4c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 상수 식이 필요합니다.
`Const` 문이 상수를 제대로 초기화하지 않거나 배열 선언이 변수를 사용하여 요소 수를 지정합니다.  
  
 **오류 ID:** BC30059  
  
### 이 오류를 해결하려면  
  
1.  선언이 `Const` 문인 경우 상수가 리터럴, 이전에 선언된 상수, 열거형 멤버 또는 리터럴, 상수 및 연산자와 결합하는 열거형 멤버의 조합을 사용하여 초기화되는지 확인합니다.  
  
2.  선언에서 배열을 지정하는 경우 변수를 사용하여 요소 수를 지정하는지 확인합니다. 그렇다면 변수를 상수 식으로 바꿉니다.  
  
## 참고 항목  
 [Const Statement](/dotnet/visual-basic/language-reference/statements/const-statement)   
 [NOTINBUILD 배열 변수](http://msdn.microsoft.com/ko-kr/c2da78bd-6928-46ba-805f-44f819dfaf93)