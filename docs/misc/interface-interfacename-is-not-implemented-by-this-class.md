---
title: "&#39;&lt;interfacename&gt;&#39; 인터페이스가 이 클래스에서 구현되지 않았습니다. | Microsoft Docs"
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
  - "bc31035"
  - "vbc31035"
helpviewer_keywords: 
  - "BC31035"
ms.assetid: 99ddabb5-20e0-4cf6-a8d4-1ca91f3c7511
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename&gt;&#39; 인터페이스가 이 클래스에서 구현되지 않았습니다.
이 클래스 또는 구조체의 멤버가 클래스 또는 구조체에서 구현하지 않는 인터페이스의 멤버를 구현하려고 합니다.  
  
 **오류 ID:** BC31035  
  
### 이 오류를 해결하려면  
  
-   클래스 또는 구조체의 시작 부분에 `Implements` 문을 추가하여 해당 인터페이스를 구현하도록 합니다.  
  
-   이 오류가 발생한 멤버에서 `Implements` 키워드를 제거합니다.  
  
## 참고 항목  
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)