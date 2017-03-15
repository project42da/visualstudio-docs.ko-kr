---
title: "&#39;ReDim&#39;으로 차수를 변경할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrArray_RankMismatch"
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReDim&#39;으로 차수를 변경할 수 없습니다.
작업에서 `ReDim` 문을 사용하여 배열 차수\(차원 수\)를 변경하려고 합니다.`ReDim`은 이전에 선언된 배열의 차원 크기를 하나 이상 변경할 수 있지만 배열 차수를 변경할 수는 없습니다.  
  
### 이 오류를 해결하려면  
  
-   해당 차원의 크기가 아닌 배열의 차수를 변경하려는지 확인하고 가능한 경우 `Dim`을 사용하여 원하는 차수의 새 배열을 선언합니다.  
  
## 참고 항목  
 [NOTINBUILD Visual Basic의 배열 개요](http://msdn.microsoft.com/ko-kr/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [NOTINBUILD Visual Basic의 다차원 배열](http://msdn.microsoft.com/ko-kr/d92cad25-07e2-4d79-8ea4-ab269700f5de)   
 [ReDim Statement](/dotnet/visual-basic/language-reference/statements/redim-statement)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)