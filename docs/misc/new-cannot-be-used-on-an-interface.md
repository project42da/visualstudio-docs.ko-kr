---
title: "&#39;New&#39;는 인터페이스에 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30375"
  - "bc30375"
helpviewer_keywords: 
  - "BC30375"
ms.assetid: c1e06108-1b52-4cbe-8cae-e816a0dbac0b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;New&#39;는 인터페이스에 사용할 수 없습니다.
[Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)에서는 인터페이스 형식이 될 변수를 선언할 때 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 절을 사용합니다.  
  
 인터페이스는 참조 형식이지만 인스턴스를 만들 수 없습니다.`New`는 클래스 또는 구조체의 인스턴스를 만드는 데만 사용할 수 있습니다.  
  
 **오류 ID:** BC30375  
  
### 이 오류를 해결하려면  
  
1.  변수가 인터페이스 형식이 되려면 `New` 키워드를 제거합니다.  
  
2.  변수가 인스턴스를 참조하려면 변수가 클래스 또는 구조체 형식이 되도록 선언합니다. 인스턴스를 만들도록 `New` 키워드를 보존합니다.  
  
## 참고 항목  
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)