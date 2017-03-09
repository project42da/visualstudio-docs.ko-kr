---
title: "제약 조건 형식 &#39;&lt;typename&gt;&#39;이 이 형식 매개 변수에 대해 이미 지정되어 있습니다. | Microsoft Docs"
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
  - "BC32071"
  - "vbc32071"
helpviewer_keywords: 
  - "BC32071"
ms.assetid: 6b0e85e9-3ac8-4181-97de-ca690b95a63c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제약 조건 형식 &#39;&lt;typename&gt;&#39;이 이 형식 매개 변수에 대해 이미 지정되어 있습니다.
제약 조건 목록에 클래스 또는 인터페이스 제약 조건이 두 번 이상 포함되어 있습니다.  
  
 제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대해 요구 사항을 적용합니다. 다음 요구 사항을 임의로 조합해서 지정할 수 있습니다.  
  
-   형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.  
  
-   형식 인수는 최대 하나의 클래스에서 상속해야 합니다.  
  
 형식은 동일한 형식에서 두 번 이상 상속하거나 구현될 수 없으며, 동일한 제약 조건 목록에 형식을 두 번 이상 지정할 수 없습니다.  
  
 **오류 ID:** BC32071  
  
### 이 오류를 해결하려면  
  
-   동일한 클래스 또는 인터페이스의 중복 지정을 모두 제거합니다. 제약 조건 목록에 한 번만 표시되어야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)