---
title: "&#39;&lt;typename&gt;&#39; 형식은 직접 또는 간접적으로 자신에게서 상속되므로 지원되지 않습니다. | Microsoft Docs"
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
  - "bc30916"
  - "vbc30916"
helpviewer_keywords: 
  - "BC30916"
ms.assetid: cea33daf-1971-4b70-a01d-7d8b5c9e4269
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 직접 또는 간접적으로 자신에게서 상속되므로 지원되지 않습니다.
클래스 또는 인터페이스가 자체적으로, 또는 해당 클래스 또는 인터페이스에서 궁극적으로 상속하는 다른 클래스 또는 인터페이스에서 상속합니다.  
  
 Visual Basic에서는 순환 상속을 지원하지 않습니다.  
  
 **오류 ID:** BC30916  
  
### 이 오류를 해결하려면  
  
-   다른 클래스 또는 인터페이스에서 상속하지 않는 기본 클래스 또는 인터페이스를 기반으로 하도록 상속 구조를 변경합니다.  
  
## 참고 항목  
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)