---
title: "&#39;&lt;membername&gt;&#39;이 여러 기본 인터페이스에 있습니다. | Microsoft Docs"
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
  - "vbc31040"
  - "bc31040"
helpviewer_keywords: 
  - "BC31040"
ms.assetid: c1a80d64-3986-417f-af92-412183e490ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39;이 여러 기본 인터페이스에 있습니다.
'\<membername\>'이 여러 기본 인터페이스에 있습니다. 파생 인터페이스 이름 대신 'Implements' 절에서 '\<membername\>'을 선언하는 인터페이스 이름을 사용하세요.  
  
 이 인터페이스는 여러 인터페이스에서 동일한 이름이 있는 멤버를 상속하여 모호성을 만듭니다.  
  
 **오류 ID:** BC31040  
  
### 이 오류를 해결하려면  
  
-   파생된 인터페이스의 이름 대신 `Implements` 절에서 정의하는 인터페이스 이름을 사용합니다.  
  
## 참고 항목  
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)