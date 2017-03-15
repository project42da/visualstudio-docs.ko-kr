---
title: "&#39;New&#39;는 &#39;MustInherit&#39;으로 선언된 클래스에 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30569"
  - "bc30569"
helpviewer_keywords: 
  - "BC30569"
ms.assetid: 94c9e6a3-6489-4d58-b7e5-7b4203677e3b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;New&#39;는 &#39;MustInherit&#39;으로 선언된 클래스에 사용할 수 없습니다.
`MustInherit` 클래스는 직접 인스턴스화될 수 없으므로 `New` 연산자는 `MustInherit` 클래스에서 사용할 수 없습니다. 컴파일 시간 형식이 `MustInherit`인 변수 및 값을 가질 수 있지만 이러한 변수 및 값은 반드시 null 값이거나 `MustInherit` 형식에서 파생된 일반 클래스의 인스턴스에 대한 참조를 포함합니다.  
  
 **오류 ID:** BC30569  
  
### 이 오류를 해결하려면  
  
-   `New` 연산자를 제거합니다.  
  
## 참고 항목  
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)