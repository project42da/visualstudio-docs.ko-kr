---
title: "이 형식 매개 변수에 대한 제약 조건이 &#39;|1&#39;의 다른 부분 형식(Partial Type) 중 하나에 정의된 해당 형식 매개 변수에 대한 제약 조건과 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc30932"
  - "bc30932"
helpviewer_keywords: 
  - "BC30932"
ms.assetid: a38ca4ad-6bbf-421e-a0d7-c5e0a9029160
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 형식 매개 변수에 대한 제약 조건이 &#39;|1&#39;의 다른 부분 형식(Partial Type) 중 하나에 정의된 해당 형식 매개 변수에 대한 제약 조건과 일치하지 않습니다.
클래스 또는 구조체의 정의가 여러 선언에서 나누어져 있는 경우 컴파일러는 해당 클래스 또는 구조체를 모든 partial 선언의 합집합으로 처리합니다. 이 때문에 다양한 partial 선언에서 충돌하는 한정자 또는 형식 매개 변수 목록을 정의할 수 없습니다.  
  
 **오류 ID:** BC30932  
  
### 이 오류를 해결하려면  
  
1.  클래스 또는 구조체에 적합한 형식 매개 변수 목록을 확인합니다. 여기에는 매개 변수, 해당 순서 및 제약 조건 목록이 포함됩니다.  
  
2.  모든 부분 정의에서 동일한 형식 매개 변수 목록을 사용해야 합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)