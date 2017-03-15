---
title: "&#39;Inherits&#39;는 &#39;Class&#39; 문 안에 한 번만 사용할 수 있으며 하나의 클래스만 지정할 수 있습니다. | Microsoft Docs"
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
  - "vbc30121"
  - "bc30121"
helpviewer_keywords: 
  - "BC30121"
ms.assetid: 4ac5b018-5632-4661-8ac6-dbda2f8c4dfe
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Inherits&#39;는 &#39;Class&#39; 문 안에 한 번만 사용할 수 있으며 하나의 클래스만 지정할 수 있습니다.
둘 이상의 `Inherits` 문이 같은 클래스에 나타나거나 `Inherits` 문에서 둘 이상의 클래스를 지정합니다. 클래스는 하나의 기본 클래스에서만 상속할 수 있습니다.  
  
 **오류 ID:** BC30121  
  
### 이 오류를 해결하려면  
  
-   불필요한 `Inherits` 문을 제거하고 나머지 `Inherits` 문이 하나의 기본 클래스만 지정하는지 확인합니다.  
  
## 참고 항목  
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)