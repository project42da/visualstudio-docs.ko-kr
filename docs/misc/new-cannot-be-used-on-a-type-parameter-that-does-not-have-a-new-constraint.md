---
title: "&#39;New&#39; 제약 조건이 없는 형식 매개 변수에는 &#39;New&#39;를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc32046"
  - "vbc32046"
helpviewer_keywords: 
  - "BC32046"
ms.assetid: 7ec6b52d-6fd5-47a0-b4a2-163bfd3dae35
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;New&#39; 제약 조건이 없는 형식 매개 변수에는 &#39;New&#39;를 사용할 수 없습니다.
선언문은 형식 매개 변수를 만들 형식으로 지정하여 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 절을 사용하는데, 형식 매개 변수가 `New` 제약 조건 없이 선언되었습니다.  
  
 형식 매개 변수의 *제약 조건*은 제네릭 형식을 만들 때 해당 형식 매개 변수에 전달되는 형식 인수에 요구 사항을 적용합니다.`New` 제약 조건은 해당 형식 인수에서 만드는 코드가 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 한다는 것을 지정합니다. 이렇게 하면 선언문의 `New` 절에서 해당 형식의 인스턴스를 만들 수 있습니다.  
  
 **오류 ID:** BC32046  
  
### 이 오류를 해결하려면  
  
-   형식 인수가 액세스할 수 있는 매개 변수가 없는 생성자를 노출하도록 요구할 수 있는 경우 형식 매개 변수 선언에 `New` 제약 조건을 추가합니다.  
  
-   형식 인수가 액세스할 수 있는 매개 변수가 없는 생성자를 노출하도록 요구할 수 없는 경우 선언문에서 `New` 절을 제거합니다. 해당 형식 매개 변수에 전달된 형식 인수가 인스턴스 생성을 허용하도록 보장할 수 없습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)