---
title: "제네릭 형식 또는 메서드에 형식 인수를 지정하는 경우에는 &#39;Of&#39;가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32093"
  - "vbc32093"
helpviewer_keywords: 
  - "BC32093"
ms.assetid: 9a1baf12-a4a4-442d-9baa-852ad30a956b
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 형식 또는 메서드에 형식 인수를 지정하는 경우에는 &#39;Of&#39;가 필요합니다.
문이 [Of](/dotnet/visual-basic/language-reference/statements/of-clause) 절을 사용하지 않고 제네릭 형식에서 형식을 생성하거나 제네릭 메서드를 호출하려고 합니다.  
  
 제네릭 형식에 대한 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 구문에서는 형식 매개 변수 및 형식 인수가 `Of` 키워드로 정의되어야 합니다. 또한 형식 매개 변수 목록 또는 형식 인수 목록을 괄호로 묶어야 합니다.  
  
 **오류 ID:** BC32093  
  
### 이 오류를 해결하려면  
  
-   형식 인수 목록의 시작 부분에 `Of` 키워드를 포함하고 전체 목록을 괄호로 묶습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [방법: 제네릭 클래스 사용](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)