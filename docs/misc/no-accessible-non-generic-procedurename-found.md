---
title: "제네릭이 아닌 액세스 가능한 &#39;&lt;procedurename&gt;&#39;이 없습니다. | Microsoft Docs"
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
  - "vbc32117"
  - "bc32117"
helpviewer_keywords: 
  - "BC32117"
ms.assetid: a7bf8b67-8a0a-499e-9992-dc00e09b7ff4
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭이 아닌 액세스 가능한 &#39;&lt;procedurename&gt;&#39;이 없습니다.
문에서 오버로드된 버전이 둘 이상 있는 프로시저를 호출하지만 모든 오버로드 버전이 제네릭이고 호출에서 형식 인수를 제공하지 않습니다.  
  
 제네릭 버전이 하나뿐이고 형식 인수 없이 호출하는 경우 컴파일러에서 *형식 유추*를 시도할 수 있습니다. 자세한 내용은 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)의 "형식 유추"를 참조하세요. 그러나 제네릭 버전이 여러 개인 경우 형식 인수를 제공하지 않으면 컴파일러에서 그중 하나를 선택할 수 없습니다. 형식 인수를 하나 제공한 경우 모든 형식 매개 변수에 대해 오버로드 버전에서 정의한 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC32117  
  
### 이 오류를 해결하려면  
  
-   형식 인수 목록과 함께 프로시저를 호출합니다.  
  
## 참고 항목  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)