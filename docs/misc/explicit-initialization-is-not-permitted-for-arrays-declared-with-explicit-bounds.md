---
title: "명시적 범위로 선언된 배열은 명시적으로 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30672"
  - "vbc30672"
helpviewer_keywords: 
  - "BC30672"
ms.assetid: 4b525e8d-bde5-4408-8c10-7605ca039f0e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 명시적 범위로 선언된 배열은 명시적으로 초기화할 수 없습니다.
특정 크기로 선언된 배열은 초기화할 수 없습니다.  
  
 **오류 ID:** BC30672  
  
### 이 오류를 해결하려면  
  
-   배열을 선언한 다음 별도로 초기화합니다.  
  
-   동적 배열로 선언 및 초기화하고 필요한 경우 `ReDim`을 사용합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    Dim A() As Integer = {0, 1, 2, 3} ReDim Preserve A(3)  
    ```  
  
## 참고 항목  
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)