---
title: "&#39;Sub New&#39;는 인터페이스에서 선언할 수 없습니다. | Microsoft Docs"
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
  - "bc30363"
  - "vbc30363"
helpviewer_keywords: 
  - "BC30363"
ms.assetid: 371d9aa8-a935-48ce-ada2-0a69ba20e070
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Sub New&#39;는 인터페이스에서 선언할 수 없습니다.
인터페이스 내에서 `Sub New`를 선언하려고 했습니다. 생성자이므로 `Sub New`는 클래스를 만들 때 한 번만 실행할 수 있습니다. 동일한 클래스나 파생 클래스에 있는 다른 생성자의 첫 번째 코드 줄이 아닌 위치에서 명시적으로 호출할 수 없습니다.  
  
 **오류 ID:** BC30363  
  
### 이 오류를 해결하려면  
  
-   `Sub New`를 제거하거나 코드의 더 적절한 위치로 이동합니다.  
  
## 참고 항목  
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)