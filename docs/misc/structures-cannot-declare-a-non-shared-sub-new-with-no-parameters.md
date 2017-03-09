---
title: "구조체에는 매개 변수가 없고 Shared가 아닌 &#39;Sub New&#39;를 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc30629"
  - "bc30629"
helpviewer_keywords: 
  - "BC30629"
ms.assetid: f4298ef7-85b1-4543-b764-4c3abda84baa
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구조체에는 매개 변수가 없고 Shared가 아닌 &#39;Sub New&#39;를 선언할 수 없습니다.
구조체 내에서 선언된 `Sub New` 생성자가 인수를 허용해야 하거나 `Shared` 한정자로 선언되어야 합니다.  
  
 **오류 ID:** BC30629  
  
### 이 오류를 해결하려면  
  
-   `Sub New` 생성자를 변경하여 인수를 허용하도록 합니다.  
  
-   생성자가 공유하도록 `Shared` 한정자를 적용합니다.  
  
## 참고 항목  
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [Structures](/dotnet/visual-basic/programming-guide/language-features/data-types/structures)