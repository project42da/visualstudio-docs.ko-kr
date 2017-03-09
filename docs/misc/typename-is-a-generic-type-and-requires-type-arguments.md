---
title: "&#39;&lt;typename&gt;&#39;은 제네릭 형식이므로 형식 인수를 사용해야 합니다. | Microsoft Docs"
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
  - "BC32076"
  - "vbc32076"
helpviewer_keywords: 
  - "BC32076"
ms.assetid: 57f63727-c544-4012-8f03-5d77fbdd1135
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;은 제네릭 형식이므로 형식 인수를 사용해야 합니다.
변수, 프로시저, 매개 변수 또는 함수 반환이 선언되어 제네릭 클래스 또는 구조체의 형식을 갖게 되었지만 선언에서 형식 인수가 제공되지 않습니다.  
  
 원래 모든 제네릭 클래스 및 구조체는 하나 이상의 형식 매개 변수와 함께 정의됩니다. 제네릭 형식을 사용하여 생성된 클래스 또는 구조체를 선언할 때 제네릭 형식에서 정의한 모든 형식 매개 변수의 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC32076  
  
### 이 오류를 해결하려면  
  
-   형식 목록을 `Of` 키워드로 시작하고 괄호로 묶어 선언에 추가합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Of](/dotnet/visual-basic/language-reference/statements/of-clause)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)