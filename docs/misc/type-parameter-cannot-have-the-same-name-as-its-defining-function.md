---
title: "형식 매개 변수에는 자신을 정의하는 함수와 동일한 이름을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32090"
  - "bc32090"
helpviewer_keywords: 
  - "BC32090"
ms.assetid: 02f4d82c-dcd7-44cc-b725-81e235f680f6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수에는 자신을 정의하는 함수와 동일한 이름을 사용할 수 없습니다.
제네릭 형식의 형식 매개 변수를 제네릭 형식과 동일한 이름으로 선언했습니다.  
  
 제네릭 형식의 형식 매개 변수 목록에서 각 형식 매개 변수 이름은 다음 이름과 모두 구별되어야 합니다.  
  
-   동일한 형식 매개 변수 목록에 있는 다른 모든 형식 매개 변수  
  
-   포함하는 제네릭 형식의 형식 매개 변수 목록에 있는 모든 형식 매개 변수  
  
-   제네릭 형식 자체의 이름입니다.  
  
 **오류 ID:** BC32090  
  
### 이 오류를 해결하려면  
  
-   이 도움말 페이지의 목록에 명시된 모든 이름과 구별되도록 형식 매개 변수의 이름을 바꿉니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)