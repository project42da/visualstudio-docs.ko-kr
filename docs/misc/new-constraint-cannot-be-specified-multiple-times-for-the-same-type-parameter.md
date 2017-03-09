---
title: "동일한 형식 매개 변수에는 &#39;New&#39; 제약 조건을 여러 번 지정할 수 없습니다. | Microsoft Docs"
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
  - "vbc32081"
  - "BC32081"
helpviewer_keywords: 
  - "BC32081"
ms.assetid: afcb30da-3973-4452-9cf3-c027f9866589
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 동일한 형식 매개 변수에는 &#39;New&#39; 제약 조건을 여러 번 지정할 수 없습니다.
제약 조건 목록에 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 제약 조건이 두 번 이상 포함되어 있습니다.  
  
 형식 매개 변수에 대한 제약 조건 목록에서 해당 형식 매개 변수로 전달된 형식 인수에서 만드는 코드가 액세스할 수 있는, 매개 변수 없는 생성자를 노출하도록 지정할 수 있습니다. 형식이 매개 변수가 없는 생성자를 한 개만 가질 수 있으므로 이 요구 사항을 두 번 이상 지정할 수 없습니다.  
  
 **오류 ID:** BC32081  
  
### 이 오류를 해결하려면  
  
-   중복된 `New` 키워드를 모두 제거합니다. 제약 조건 목록에 하나만 있어야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)