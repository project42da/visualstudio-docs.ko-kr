---
title: "&#39;&lt;typeargumentname&gt;&#39; 형식 인수가 &#39;&lt;typeparametername&gt;&#39; 제약 조건 형식에서 상속하거나 이를 구현하지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32044"
  - "vbc32044"
helpviewer_keywords: 
  - "BC32044"
ms.assetid: be91f648-c07d-4991-8ed1-28b1327619c4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeargumentname&gt;&#39; 형식 인수가 &#39;&lt;typeparametername&gt;&#39; 제약 조건 형식에서 상속하거나 이를 구현하지 않습니다.
제네릭 형식에 제공되는 형식 인수가 해당 형식 매개 변수에 대한 상속 또는 구현 제약 조건을 충족하지 않습니다.  
  
 제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대해 요구 사항을 적용합니다. 가능한 요구 사항에는 다음이 포함됩니다.  
  
-   형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.  
  
-   형식 인수는 최대 하나의 클래스에서 상속해야 합니다.  
  
 단일 형식 매개 변수에 대해 앞의 요구 사항을 결합할 수 있습니다. 코드가 제네릭 형식에 정의된 모든 형식 매개 변수에 대한 모든 제약 조건을 충족하는 형식 인수를 제공하지 않는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 형식을 만들 수 없습니다.  
  
 **오류 ID:** BC32044  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수에 대해 지정된 모든 인터페이스를 구현하고, 지정된 클래스가 있는 경우 지정된 클래스에서 상속하는 형식의 형식 인수를 선택합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [방법: 제네릭 클래스 사용](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)