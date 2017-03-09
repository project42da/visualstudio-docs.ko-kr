---
title: "&#39;&lt;delegatename&gt;&#39; 대리자에서 메서드 &#39;&lt;procedurename&gt;&#39;에 대한 형식 인수를 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc30952"
  - "bc30952"
helpviewer_keywords: 
  - "BC30952"
ms.assetid: 5eb804ce-2e93-4668-b655-7fe00815e552
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;delegatename&gt;&#39; 대리자에서 메서드 &#39;&lt;procedurename&gt;&#39;에 대한 형식 인수를 유추할 수 없습니다.
대입문이 `AddressOf`를 사용하여 제네릭 프로시저의 주소를 대리자에게 할당하지만 형식 인수를 제네릭 프로시저에 제공하지 않습니다.  
  
 일반적으로 제네릭 형식을 호출하는 경우 제네릭 형식이 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다. 형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다. 컨텍스트가 컴파일러가 형식을 유추할 수 있는 충분한 정보를 제공하지 않는 경우 오류가 생성됩니다.  
  
 **오류 ID:** BC30952  
  
### 이 오류를 해결하려면  
  
-   `AddressOf` 식에서 제네릭 프로시저에 대한 형식 인수를 지정합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)