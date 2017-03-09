---
title: "메서드/여러 줄 람다 외부에서는 레이블을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30016"
  - "bc30016"
helpviewer_keywords: 
  - "BC30016"
ms.assetid: 17d12a96-d759-4df9-882c-5e45c1d814a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 메서드/여러 줄 람다 외부에서는 레이블을 사용할 수 없습니다.
`Sub`, `Function`, 속성 `Get` 또는 속성 `Set` 프로시저 내에서만 문에 레이블을 추가할 수 있습니다. 실행 가능 문에만 레이블을 추가할 수 있고 모든 실행 가능 문은 프로시저 내에 있어야 합니다.  
  
 **오류 ID:** BC30016  
  
### 이 오류를 해결하려면  
  
1.  문에서 레이블을 제거하거나 프로시저 내에서 문을 이동합니다.  
  
## 참고 항목  
 [How to: Label Statements](../Topic/How%20to:%20Label%20Statements%20\(Visual%20Basic\).md)   
 [Sub Statement](/dotnet/visual-basic/language-reference/statements/sub-statement)   
 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)