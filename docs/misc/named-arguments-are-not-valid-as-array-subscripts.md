---
title: "명명된 인수는 배열 첨자로 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30075"
  - "bc30075"
helpviewer_keywords: 
  - "BC30075"
ms.assetid: a25025c9-0763-4c19-9e9b-cffb9aacaa8a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 명명된 인수는 배열 첨자로 사용할 수 없습니다.
이름으로 프로시저 인수를 전달하기 위한 구문\(예: `Array(Index := 10)`\)을 사용하여 배열 인덱스를 지정합니다. 이 구문은 배열 첨자에 사용할 수 없습니다.  
  
 **오류 ID:** BC30075  
  
### 이 오류를 해결하려면  
  
-   일반 변수 또는 상수 식을 배열 인덱스로 사용합니다\(예: `Array(10)`\).  
  
## 참고 항목  
 [NOTINBUILD Visual Basic의 배열 개요](http://msdn.microsoft.com/ko-kr/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)