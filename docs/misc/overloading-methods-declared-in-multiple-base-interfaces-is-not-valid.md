---
title: "여러 기본 인터페이스에 선언된 메서드를 오버로드할 수 없습니다. | Microsoft Docs"
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
  - "bc31410"
  - "vbc31410"
helpviewer_keywords: 
  - "BC31410"
ms.assetid: 7d1831c2-837c-4b02-8492-d0fc038fe184
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 여러 기본 인터페이스에 선언된 메서드를 오버로드할 수 없습니다.
여러 개의 상속된 인터페이스가 암시적으로 동일한 메서드를 오버로드합니다.  
  
 **오류 ID:** BC31410  
  
### 이 오류를 해결하려면  
  
-   `Overloads` 한정자 대신 `Shadows` 한정자를 사용합니다.  
  
## 참고 항목  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)