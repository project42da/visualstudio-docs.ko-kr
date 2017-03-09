---
title: "메서드 본문의 첫째 문은 메서드 선언과 같은 줄에 있을 수 없습니다. | Microsoft Docs"
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
  - "vbc30040"
  - "bc30040"
helpviewer_keywords: 
  - "BC30040"
ms.assetid: 27df3488-de77-499d-b9a6-08037d540cb0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 메서드 본문의 첫째 문은 메서드 선언과 같은 줄에 있을 수 없습니다.
`Function`, `Sub`, `Get`, `Set` 또는 `Property` 문은 소스 코드 줄에 단독으로 있어야 합니다.  
  
 **오류 ID:** BC30040  
  
### 이 오류를 해결하려면  
  
1.  프로시저 선언 앞에 있는 모든 줄 레이블을 제거합니다.  
  
2.  프로시저 선언 앞에 있는 모든 문을 이전 소스 코드 줄로 이동합니다.  
  
3.  프로시저 선언 다음에 오는 모든 문을 후속 소스 코드 줄로 이동합니다.  
  
## 참고 항목  
 [Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/index)   
 [How to: Label Statements](../Topic/How%20to:%20Label%20Statements%20\(Visual%20Basic\).md)