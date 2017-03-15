---
title: "&lt;error&gt;: &#39;&lt;classname1&gt;&#39;이 &#39;&lt;classname2&gt;&#39;에서 상속됩니다. | Microsoft Docs"
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
  - "bc30256"
  - "vbc30256"
helpviewer_keywords: 
  - "BC30256"
ms.assetid: 170a12ee-87ef-4a49-8c84-ebf57fac435e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;error&gt;: &#39;&lt;classname1&gt;&#39;이 &#39;&lt;classname2&gt;&#39;에서 상속됩니다.
순환 상속 계층 구조가 발견되었습니다. 클래스가 자체적으로, 또는 해당 클래스에서 직접 또는 궁극적으로 상속되는 다른 클래스에서 상속하도록 디자인되었습니다.  
  
 이 메시지는 순환 상속 경로를 추적할 수 있도록 두 번 이상 나타날 수 있습니다.  
  
 **오류 ID:** BC30256  
  
### 이 오류를 해결하려면  
  
-   순환 상속 경로에서 하나 이상의 `Inherits` 문을 제거하여 순환을 중단합니다.  
  
## 참고 항목  
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)