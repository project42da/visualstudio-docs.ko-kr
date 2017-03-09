---
title: "지정한 개수의 형식 인수를 허용하는 액세스 가능한 &#39;&lt;genericprocedurename&gt;&#39;이 없습니다. | Microsoft Docs"
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
  - "bc32118"
  - "vbc32118"
helpviewer_keywords: 
  - "BC32118"
ms.assetid: 4ee942ba-0fa1-4ec1-9c2c-a0c0dc3f1b17
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 지정한 개수의 형식 인수를 허용하는 액세스 가능한 &#39;&lt;genericprocedurename&gt;&#39;이 없습니다.
문에서 오버로드된 버전이 둘 이상 있는 제네릭 프로시저를 호출하지만 호출에서 제공된 형식 인수 개수와 동일한 개수의 형식 매개 변수를 정의하는 오버로드된 버전이 없습니다.  
  
 제네릭 버전이 하나뿐인 경우 형식 인수 없이 호출하며, 컴파일러에서 *형식 유추*를 시도할 수 있습니다. 자세한 내용은 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)의 "형식 유추"를 참조하세요. 그러나 제네릭 버전이 여러 개인 경우 형식 인수를 제공하지 않으면 컴파일러에서 그중 하나를 선택할 수 없습니다. 형식 인수를 하나 제공한 경우 모든 형식 매개 변수에 대해 오버로드 버전에서 정의한 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC32118  
  
### 이 오류를 해결하려면  
  
-   호출하려는 오버로드된 버전을 결정하고 적절한 개수의 형식 인수를 제공합니다.  
  
## 참고 항목  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)