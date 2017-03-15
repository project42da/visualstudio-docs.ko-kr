---
title: "구조체의 멤버 중 비공유 멤버는 &#39;New&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc30795"
  - "BC30795"
helpviewer_keywords: 
  - "BC30795"
ms.assetid: 8e4e1ad8-3bac-475f-82e8-e4f134692204
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구조체의 멤버 중 비공유 멤버는 &#39;New&#39;로 선언할 수 없습니다.
구조체의 공유되지 않는 변수가 `New` 절로 선언되었습니다.  
  
 다음 코드 줄에 표시된 것처럼 구조체에서 공유되는 참조 변수를 초기화할 수 있고 초기화 없이 비공유 참조 변수를 사용할 수 있습니다.  
  
 `Shared structVar1 As New System.ApplicationException`  
  
 `Dim structVar2 As System.ApplicationException`  
  
 그러나 구조체에서 비공유 참조 변수를 초기화할 수 없습니다. 다음 코드 줄은 유효하지 않습니다.  
  
 `Dim structVar3 As New System.ApplicationException ' INVALID IN A STRUCTURE`  
  
 **오류 ID:** BC30795  
  
### 이 오류를 해결하려면  
  
-   `Shared` 한정자 또는 `New` 키워드를 참조 변수 선언에서 제거합니다.  
  
## 참고 항목  
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)