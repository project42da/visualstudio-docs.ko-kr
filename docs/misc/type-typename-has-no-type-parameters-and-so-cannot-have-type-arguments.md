---
title: "&#39;&lt;typename&gt;&#39; 형식에는 형식 매개 변수가 없으므로 형식 인수를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc32045"
  - "vbc32045"
helpviewer_keywords: 
  - "BC32045"
ms.assetid: b86e784c-6718-4585-bd39-2f0982068828
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식에는 형식 매개 변수가 없으므로 형식 인수를 사용할 수 없습니다.
선언 또는 대입문은 제네릭이 아닌 형식을 호출할 때 [Of](/dotnet/visual-basic/language-reference/statements/of-clause) 절을 포함합니다.  
  
 해당 정의에 따르면 *제네릭 형식*은 하나 이상의 *형식 매개 변수*를 통해 지정할 수 있는 데이터 형식에서 작동하는 클래스, 구조체, 인터페이스, 프로시저 또는 대리자입니다. 사용하는 코드가 형식을 이 제네릭 형식에서 만드는 경우 *형식 인수*를 각 형식 매개 변수에 제공합니다. 형식을 만들 때, 생성된 코드에서 형식 매개 변수가 발생할 때마다 이에 해당하는 형식 인수로 바꿉니다.  
  
 형식 매개 변수는 괄호 안의 `Of` 절로 정의되고, 형식 인수는 괄호 안의 `Of` 절을 사용하여 제공합니다.`Of` 절은 제네릭 형식에서만 사용합니다.  
  
 제네릭이 아닌 형식은 형식 매개 변수를 허용하지 않습니다. 이러한 형식을 호출할 때 형식 인수를 지정할 수 없습니다.  
  
 **오류 ID:** BC32045  
  
### 이 오류를 해결하려면  
  
1.  선언이나 대입문에 사용하고 있는 형식의 철자를 확인합니다.  
  
2.  제네릭이 아닌 형식을 호출하는 경우 `Of` 절 및 해당 괄호가 있으면 이를 제거합니다. 프로시저, 대리자 또는 클래스 생성자의 경우 표준 인수 목록을 묶는 괄호를 제거하지 마세요.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [방법: 제네릭 클래스 사용](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)