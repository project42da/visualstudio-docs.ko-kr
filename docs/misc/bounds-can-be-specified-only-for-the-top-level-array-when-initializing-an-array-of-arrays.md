---
title: "배열의 배열을 초기화하는 동안에는 최상위 배열에 대해서만 범위를 지정할 수 있습니다. | Microsoft Docs"
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
  - "bc32014"
  - "vbc32014"
helpviewer_keywords: 
  - "BC32014"
ms.assetid: d8d7155d-82d1-4a25-b9bb-1883e1586383
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열의 배열을 초기화하는 동안에는 최상위 배열에 대해서만 범위를 지정할 수 있습니다.
가변 배열\(배열의 배열\)에 대한 배열 초기화가 하위 수준 중 하나의 초기 길이를 설정합니다. 배열 선언문에서는 최상위 배열의 길이만 지정할 수 있습니다.  
  
 **오류 ID:** BC32014  
  
### 이 오류를 해결하려면  
  
1.  최상위 배열을 제외한 모든 길이 지정을 제거합니다.  
  
2.  `New` 키워드를 사용하는 후속 대입문에서 하위 수준 배열의 초기 길이를 설정합니다.  
  
## 참고 항목  
 [NOTINBUILD 배열 변수](http://msdn.microsoft.com/ko-kr/c2da78bd-6928-46ba-805f-44f819dfaf93)   
 [NOTINBUILD Visual Basic의 가변 배열](http://msdn.microsoft.com/ko-kr/05c12439-ee8f-4fef-ba75-b35402b67ab9)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)